---
title: "Read-Only First: How Agencies Let AI Touch Live Campaigns Safely"
description: "A four-step trust ladder for agencies: let an AI agent read, then suggest, then change with approval, then act on its own, and only where a mistake is cheap."
date: "2026-10-15"
image: "https://raw.githubusercontent.com/toffu-ai/blog-posts/main/images/ai-trust-ladder-hero.png"
slug: "ai-trust-ladder-live-campaigns"
author: "Toffu"
---

"If it adds an extra zero to a budget, is there a control?"

Almost every agency asks us this in the first call. It is the right question. An AI agent that can read your ad accounts can usually also change them, and a client does not care whether a wrong budget came from a person or a model.

The agencies that roll AI out well do not answer it with one big yes or no. They climb a ladder: the agent earns each new kind of access by doing the step below it well. This post is that ladder, built from what we saw across many agency rollouts.

## Why "all or nothing" fails

There are two ways to get this wrong.

**Full access on day one.** The first week feels like magic. Then the agent makes a few mistakes on live accounts, the team stops trusting it, and every output gets checked twice. Now the tool is slower than doing the work by hand.

**Read-only forever.** Nothing breaks, but nothing gets faster either. The agent writes reports, someone still makes every change by hand, and the team decides AI is "a nicer dashboard".

The ladder sits between the two.

## Step 1: read only

The agent connects to your ad accounts, analytics and store, and only answers questions and writes reports.

Use this step to check the numbers, not to save time yet. Ask the agent for last week's spend, conversions and cost per result for a few accounts, and compare each one against the platform's own screen. When they differ, find out why before you go further. The cause is usually a filter in your view, a different conversion event or attribution window, or a different currency. Teach the agent the rule once ("exclude brand campaigns", "use purchases, not add-to-carts") and check again.

**Move up when** the numbers match on the accounts you care about, and the team stops checking every answer by hand.

## Step 2: suggest, a person acts

The agent looks for problems and proposes fixes, and a person makes the change. Good first jobs:

- **Budget pacing.** Every morning, flag accounts spending more than 10% over or under plan.
- **Search terms.** Propose negative keywords, with the terms and the spend behind each one.
- **Waste.** List ads or ad sets with spend and no results in the last 7 days.

Keep track of how many suggestions you take as they are, change, or reject. That number tells you which jobs are ready for the next step and which are not.

**Move up when** the team takes most suggestions in a job without changing them.

## Step 3: the agent acts, a person approves each change

Now the agent makes the change itself, but only after someone approves it. In Toffu, every write to an ad platform stops for approval by default. The agent shows exactly what it is about to change (which campaign, which setting, the new value) and waits for **Approve**. Approvals can come from the chat, Slack or WhatsApp, so a media buyer can approve a budget change from their phone.

Two habits make this step work:

- **Read the change, not the summary.** "Raise budget on the top campaign" is a summary. "Campaign X: daily budget 500 to 5,000" is the change. That extra zero is what you are there to catch.
- **Approve small batches.** Ten clear changes beat one approval for fifty. A long list gets approved without being read.

**Move up when** a job has run for a few weeks with approvals and nobody has had to fix anything.

## Step 4: the agent acts on its own, inside limits

For jobs that have proven themselves, the agent can run on a schedule without waiting for anyone. Choose these jobs by how much a mistake would cost, not by how often the agent gets them right:

| Cheap to get wrong | Expensive to get wrong |
|---|---|
| Adding negative keywords from an approved list | Changing budgets |
| Pausing an ad with spend and zero results for 14 days | Launching new campaigns |
| Renaming campaigns to your naming convention | Changing bids or bid strategy |
| Turning off auto-enabled platform enhancements | Editing audiences or targeting |

Keep the right-hand column at step 3. Most agencies we work with never move budgets or launches to step 4, and that is fine: the time saving is in the agent preparing the change, not in skipping the click.

Every scheduled job should report what it did. A short message after each run ("paused 3 ads, spend 1,240, zero purchases in 14 days") lets anyone spot a bad rule within a day.

## The ladder is per job, not per tool

Your agent can be at step 4 for search terms, step 3 for budgets and step 1 for a new client at the same time. That is the normal state. Write it down for your team:

- **Per job:** which step it is on, who approves, and what moves it up.
- **Per client:** new clients start at step 1, whatever the agent does for other clients.
- **Per person:** who may approve changes, and who only reads.

## It also answers your client's question

When a client's marketing or security team asks "what can this tool do to our accounts?", the ladder is your answer. Read access is used for reporting. Changes go through a named person in your team. Only low-risk jobs run on their own, and each one reports what it did. That is easier to approve than "we use AI".

## Start today

1. Connect one client's accounts in Toffu and leave approvals on.
2. Ask for last week's numbers and check them against the platforms.
3. Pick one step 2 job, budget pacing is a good first one, and run it every morning for two weeks.
4. Move each job up only when it has earned it.
