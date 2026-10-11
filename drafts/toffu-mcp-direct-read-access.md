---
title: "How to Connect Google Ads, Meta Ads, and GA4 to Claude and ChatGPT"
description: "Connect Google Ads, Meta Ads, GA4, Shopify, and 40+ marketing platforms to Claude or ChatGPT with one MCP connector. No developer tokens, no self-hosting."
date: "TBD"
image: ""
slug: "toffu-mcp-direct-read-access"
---

*Connect Google Ads, Meta Ads, GA4, Shopify, and 40+ marketing platforms to Claude or ChatGPT with one MCP connector. No developer tokens, no self-hosting.*

---

Your team already works in Claude or ChatGPT. The data they need lives somewhere else: Google Ads, Meta, GA4, Shopify, HubSpot, and five more tools after that.

## Why connecting ad platforms to Claude directly is hard

Getting that data into the AI is the hard part. Try it yourself and you'll find:

- Google's own Google Ads MCP server is self-hosted. You need a Google Cloud project, OAuth credentials, a developer token from a manager account, and somewhere to run it.
- Meta needs your own developer app. Reading accounts beyond your own means business verification and app review.
- LinkedIn's advertising API needs a separate approval to its Marketing Developer Platform.
- Many of the other platforms have no connector at all.
- The ones that do each need their own setup, login, and permissions. Each covers a different slice of the API, and their tokens expire.

That's a day of setup per platform, and weeks for the ones that need approval, before your AI answers a single question. If you run an agency, multiply it by every client.

So most people still export a CSV, paste it into the chat, and hope it's the right date range.

You can't skip the plumbing without a connector in the middle. Toffu is that connector: connect each platform in Toffu with one click, add Toffu to Claude or ChatGPT, and your AI reads all of them.

## Why Toffu as your Claude and ChatGPT marketing connector

**One connection instead of forty.** Toffu already did the approvals, app reviews, and token plumbing for every platform below. You click Connect in Toffu, add Toffu to Claude or ChatGPT, and your AI can read all of them. No developer tokens, no app reviews, no API keys pasted into a chat.

**Every account, not just yours.** Agencies get every client's accounts through the same single connection, scoped to the client you pick.

**Cross-platform answers in one conversation.** Ask "Compare last week's Meta spend with Shopify revenue by day" and your AI pulls both and lines them up. That used to be two exports and a spreadsheet.

**The full API, not a preset menu.** Most connectors expose a handful of reports someone decided you'd want. Toffu lets your AI read any endpoint the platform offers, so the odd question gets answered too: a specific asset group, a rejected ad's policy reason, a custom GA4 dimension.

**Seconds, not minutes.** A lookup goes straight to the platform. It doesn't start a full Toffu agent run, so simple questions come back fast.

**More than a data pipe.** Most connectors stop at reading data. Toffu also gives your AI a marketing agent that knows your brand, your account history, and your playbooks, and it makes changes only after you approve them, with undo.

**Nothing can break.** The data tools are read-only. Your AI can look at every campaign; it cannot change one.

## What your AI gets

Toffu's MCP server exposes the same read tools the Toffu agent uses internally:

- **List entities.** Campaigns, ad sets, ads, keywords, audiences, pages, posts, products, orders, contacts, deals, and more, on every connected platform.
- **Read any API endpoint.** When a list isn't enough, your AI calls the platform's own API directly, read-only, signed with the connection you already set up in Toffu.

## Which platforms

Every platform you connect in Toffu, including:

**Advertising:** Google Ads, Meta Ads, LinkedIn Ads, TikTok Ads, Microsoft Advertising, Reddit Ads, Pinterest Ads, Taboola, Outbrain, RTB House, Display & Video 360, Google Ad Manager

**Analytics and tracking:** Google Analytics 4, Google Tag Manager, Google Search Console, Microsoft Clarity, BigQuery, Singular, Tableau

**Commerce:** Shopify, WooCommerce, Magento, Google Merchant Center

**Social and local:** Facebook Pages, Instagram, LinkedIn, X, Reddit, Pinterest, Google Business Profile

**CRM, content, and work:** HubSpot, GoHighLevel, WordPress, Webflow, Monday, Asana, Typeform, GitHub

## Why reads only

A write tool that any AI client can call with your ad account access is one prompt injection away from a paused campaign or a budget you didn't approve. A web page, a sheet cell, or a forwarded email can carry instructions, and the model reading it may follow them.

So changes still go through Toffu's change flow: your AI proposes a change, you approve it, and you can undo it. Every change is logged. That flow is what makes it safe to connect an ad account to an AI in the first place.

## How to connect Google Ads, Meta Ads, and GA4 to Claude or ChatGPT

1. Sign up at [toffu.ai](https://toffu.ai) and connect your platforms with one click each.
2. In Claude or ChatGPT, add a custom connector with the URL `https://mcp.toffu.ai/mcp`.
3. Sign in to Toffu when asked.
4. Ask something that needs data: "Use Toffu to list my active Meta campaigns and their daily budgets."

## Read tools or the Toffu agent?

**Use the read tools** when you know what data you want: a list, a number, a raw report.

**Ask the Toffu agent** when you want a decision: why CPA went up, what to cut, what to launch next. The agent reads the same data and adds your brand, your account history, and your playbooks.

Most days you'll use both in the same conversation.
