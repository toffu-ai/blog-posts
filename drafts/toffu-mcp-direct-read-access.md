---
title: "Toffu's MCP Now Reads Every Platform Directly"
description: "Claude, ChatGPT, and any MCP client can now read your ad accounts, analytics, CRM, and store through Toffu, with no agent turn in between."
date: "TBD"
image: ""
slug: "toffu-mcp-direct-read-access"
---

*Claude, ChatGPT, and any MCP client can now read your ad accounts, analytics, CRM, and store through Toffu, with no agent turn in between.*

---

Until today, connecting Claude or ChatGPT to Toffu gave you one main path: send a message to the Toffu agent and wait for its answer. That is the right path for real work. Toffu knows your accounts, your brand, and your history, and it plans before it acts.

But a lot of the questions people ask from Claude are not real work. They are lookups. "What did we spend on Meta yesterday?" "Which Google Ads campaigns are paused?" "Pull the last 50 Shopify orders." Routing a lookup through a full agent run is slow, and it costs a run.

So we opened up the data layer.

## What's new

Toffu's MCP server now exposes the same read tools the Toffu agent uses internally:

- **List entities.** Campaigns, ad sets, ads, keywords, audiences, pages, posts, products, orders, contacts, deals, properties, and more, on every connected platform. One tool, one `platform` argument.
- **Read any API endpoint.** When the entity tools don't cover what you need, your MCP client can call the platform's own API directly, read-only, signed with the connection you already set up in Toffu.

Your client gets raw data in seconds, and you keep the Toffu agent for the work that needs judgment.

## Which platforms

Every platform you connect in Toffu, including:

**Advertising:** Google Ads, Meta Ads, LinkedIn Ads, TikTok Ads, Microsoft Advertising, Reddit Ads, Pinterest Ads, Taboola, Outbrain, RTB House, Display & Video 360, Google Ad Manager

**Analytics and tracking:** Google Analytics 4, Google Tag Manager, Google Search Console, Microsoft Clarity, BigQuery, Singular, Tableau

**Commerce:** Shopify, WooCommerce, Magento, Google Merchant Center

**Social and local:** Facebook Pages, Instagram, LinkedIn, X, Reddit, Pinterest, Google Business Profile

**CRM, content, and work:** HubSpot, GoHighLevel, WordPress, Webflow, Monday, Asana, Typeform, GitHub

If you connected it in Toffu, your MCP client can read it.

## Why reads only

Reading is safe to hand to any client. Writing is not.

A write tool that any MCP client can call with your ad account tokens is one prompt injection away from a paused campaign or a budget you didn't approve. A web page, a sheet cell, or a forwarded email can carry instructions, and the model reading it may follow them.

So changes still go through Toffu's change flow: the client proposes a change, you approve it, and you can undo it. Every change is logged. That flow is what makes it safe to connect an ad account to an AI in the first place, and we are not giving it up for convenience.

## How to use it

If you already connected Toffu to Claude or ChatGPT, there is nothing to do. The new tools appear the next time your client loads Toffu's tools.

If you haven't:

1. In Claude or ChatGPT, add a custom connector with the URL `https://mcp.toffu.ai/mcp`.
2. Sign in to Toffu when asked.
3. Ask a question that needs data, for example: "Use Toffu to list my active Meta campaigns and their daily budgets."

## When to use which

**Use the read tools** when you know what data you want: a list, a number, a raw report.

**Ask the Toffu agent** when you want an answer: why CPA went up, what to cut, what to launch next, or a report built across five platforms. The agent uses the same data, plus your brand, your history, and your skills.

Most days you will use both in the same conversation. That is the point.
