---
title: "We Taught Toffu to Fix Toffu"
description: "When the agent finds a bug in itself, it can now trigger Cursor to fix it. Here's how we wired two AI systems together."
date: "2026-02-24"
author:
  name: "Or Arbel"
  pic_url: "https://cdn-uw2.toffu.ai/img/or.jpeg"
  twitter_url: "https://x.com/orarbel"
  linkedin_url: "https://www.linkedin.com/in/orarbel/"
tags:
  - ai-agents
  - cursor
  - engineering
---

Toffu is an AI agent. Cursor is an AI coding tool. For a while, when Toffu found a bug in itself mid-session, I'd have to stop, switch to Cursor, re-explain the context, and tell it what to fix. The agent had already done the hard part - identified the problem, traced the call stack, figured out the root cause - but that context died the moment I left the chat.

So we built a tool that lets Toffu tell Cursor to fix it.

## What it does

When I type "fix in cursor" in a Toffu session, the agent calls `trigger_cursor_agent`. The tool:

1. Reads the current session - the last 20 messages, recent tool calls, and anything that looks like an error
2. Packages that into a structured prompt for Cursor's background agents API
3. Posts it to `https://api.cursor.com/v0/agents` with `autoCreatePr: true`
4. Returns a job ID

Cursor picks up the job, clones the repo, reads the context, finds the relevant code, and opens a PR with the fix. I get a link to review.

The whole thing takes under a minute. The fix is minimal - the prompt is explicit about that.

## The context problem

The reason this works better than manually switching tools is the context handoff.

By the time I say "fix in cursor," Toffu has already called 5-10 tools against the codebase, hit errors, read files, and built up a mental model of the bug. None of that exists in a Cursor chat window.

The `_get_session_context` function collects three things from the MongoDB session document:

- **Tool calls** - what Toffu tried, including args. If it ran `get_google_ads_campaigns` and got a `KeyError`, that's in there.
- **Errors** - tool results that contain "error", "exception", "failed", or "traceback" are extracted separately and highlighted in the prompt.
- **Recent messages** - the last 6 user/assistant turns, truncated to 500 chars each.

This gets assembled into a prompt that tells Cursor exactly what was being debugged, what was tried, and what broke. It's the difference between "fix this function" and "we were trying to do X, called Y, it failed because Z, here's the stack trace."

## The minimal fix constraint

Early versions of the prompt just described the bug and asked Cursor to fix it. The result was PRs that fixed the bug but also refactored surrounding code, renamed things, and added logging. Not what you want when you're trying to understand exactly what changed.

The current prompt is explicit:

```
CRITICAL: Use the most minimal fix possible. Change only what is strictly necessary to resolve the issue. Do not refactor, reorganize, or improve unrelated code. Prefer single-line fixes over multi-line changes when both solve the problem.
```

It also explicitly says: do not push, do not create commits - just make the change. The `autoCreatePr: true` flag handles the PR separately once Cursor is done.

This matters. A one-line fix in a PR is easy to review. A 40-line PR where 35 lines are incidental cleanup is not.

## The repo routing

The tool takes an `issue_type` parameter - either `"backend"` or `"frontend"` - which maps to the right GitHub repo:

```python
REPO_MAPPING = {
    "backend": "toffu-api",
    "frontend": "toffu-chat",
}
```

The agent decides which one based on what it was debugging. If it was tracing a Python error through the API server, it routes to `toffu-api`. If it was looking at a React component, it routes to `toffu-chat`.

## What actually happens

In practice the workflow looks like this: I'm in a Toffu session debugging why a particular tool is returning malformed data. Toffu traces it through three layers, finds the bug - a dict key is wrong in a transformation function. I say "fix in cursor, it's a backend issue." Toffu calls `trigger_cursor_agent`, passes the issue description and the session context. A minute later there's a PR that changes one line in the right file.

Most of the time the fix is correct. Sometimes Cursor misidentifies which call site is authoritative and patches the wrong layer. When that happens, the PR still makes the review easy because the context is right there in the PR body and I can redirect quickly.

## The access control

The tool is gated to the Toffu team via `USER_SPECIFIC_TOOLS`. Triggering background agents that write code and open PRs against our production repos isn't something we want available to all users - the blast radius is too high. It's a power tool for people who understand what's happening under the hood. The UX is also unfinished: the Cursor API doesn't yet return a direct link to the PR in its response, so you get a job ID and have to find the PR manually.

---

The implementation is about 200 lines. Most of it is context formatting. The actual API call is 20 lines. The interesting part was figuring out what context is actually useful to pass - tool calls and errors turned out to matter more than the conversation text.
