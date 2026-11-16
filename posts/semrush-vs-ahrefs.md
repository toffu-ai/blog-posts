---
title: "Ahrefs vs Semrush (2026): Pricing, Data and API Access Compared"
seoTitle: "Ahrefs vs Semrush (2026): Pricing, API and Which to Pick"
author: "Toffu Team"
description: "Ahrefs vs Semrush with prices checked on 16 Nov 2026: plans, seats, API and MCP access for AI agents, and which one an agency should pay for."
date: 2025-01-07
image: https://cdn-uw2.toffu.ai/68594b73894454f695c17c39/images/semrush-vs-ahrefs-hero.png
---

# Ahrefs vs Semrush

*Updated 16 November 2026. Every price and plan limit below was checked on the vendors' own pricing and help pages on that date.*

Short answer: **pick Ahrefs if links and organic research are the job. Pick Semrush if you also sell PPC, local or content work and want one vendor for all of it.** At the entry tier they cost about the same. The differences that cost agencies money show up later: extra seats, data history, and whether the tool will feed data to the AI agents and reports you already run.

Most comparisons stop at feature lists. This one focuses on the three things we had to work out when we connected both tools to [Toffu](https://toffu.ai/tools/ahrefs): what you actually pay per seat, what history you get, and what it takes to get the data out through an API or MCP server.

## Pricing, checked 16 November 2026

| | Ahrefs | Semrush |
|---|---|---|
| Free option | Ahrefs Free (data on sites you own and verify) | Free plan: 1 demo project, 10 reports per day |
| Cheapest paid plan | Starter, $29/mo | SEO, $139/mo ($117.33/mo billed yearly) |
| Main tiers | Lite $129, Standard $249, Advanced $449 | Starter $199, Pro+ $299 |
| Top tier | Enterprise, custom | Advanced, custom |
| Extra users | $40 (Lite), $60 (Standard), $80 (Advanced) per user/mo | From $45 per user/mo |
| Tracked keywords | 750 / 2,000 / 5,000 | 500 / 500 / 1,500 / 5,000+ |
| Historical data | 6 months (Lite), 2 years (Standard), 5 years (Advanced) | "Historical SEO data" listed from Pro+ |
| Yearly discount | Up to 17% | About 16% on the SEO plan |

Sources: [ahrefs.com/pricing](https://ahrefs.com/pricing) and [semrush.com/prices](https://www.semrush.com/prices/).

Three things the table hides:

- **Semrush renamed its plans.** If a guide quotes Pro, Guru and Business, it is out of date. The current tiers are SEO, Starter, Pro+ and Advanced, and AI visibility tracking is part of every paid tier.
- **Ahrefs Lite caps history at 6 months.** For year-over-year client reports you need Standard ($249). This is the most common reason agencies outgrow Lite.
- **Seats add up fast.** A 4-person team on Ahrefs Standard pays $249 + 3 × $60 = $429/mo. Do the seat math before you compare headline prices.

## Data: stop comparing index sizes

Both vendors publish big numbers about their keyword and backlink databases. They measure them in different ways, and the numbers change every quarter. Picking a tool on database size is like picking a bank on the size of its logo.

What actually matters is whether each tool sees *your* market:

1. Take 3 clients' domains and 1 competitor each.
2. Compare each tool's referring-domain counts and top keywords with what you know from Google Search Console.
3. Keep the tool that is closest on the sites you know.

Our experience: Ahrefs is the stronger tool for link work (Link Intersect, new and lost links, broken backlinks). Semrush is the broader suite: on top of SEO it sells separate toolkits for advertising, local, content and social. Both run competent site audits.

## API and MCP access: the difference most comparisons miss

In 2026 a lot of SEO work runs through AI agents and automated reports, not through the tool's own UI. Here the rules are very different:

| | Ahrefs | Semrush |
|---|---|---|
| Plans with API access | Lite and higher | One Starter, One Pro+, Classic Pro, Classic Guru (50,000 units included); Business and Advanced need a units package |
| Units included | Lite 200,000, Standard 800,000, Advanced 2,000,000 per month | 50,000, refreshed at renewal |
| MCP server | Yes, uses the same API units | Yes (`mcp.semrush.com/v2/mcp`), uses the same API units |
| Rows per request | 100 (Lite) to 500 (Advanced) | Depends on the report |

Sources: [Ahrefs API v3 help article](https://help.ahrefs.com/en/articles/6559232-about-api-v3) and [Semrush MCP docs](https://developer.semrush.com/api/introduction/semrush-mcp).

We hit this ourselves. When we asked Toffu to pull Domain Rating for two domains from the Ahrefs key on our own workspace on 16 November 2026, the API answered:

```
GET /v3/site-explorer/domain-rating?target=toffu.ai
403 {"error": "Insufficient plan"}
```

The fix is plan-level, not a bug in your script. If you plan to put either tool behind an AI agent, a Looker Studio connector or a reporting pipeline, check the API row of your plan before you buy. Ahrefs older help pages still say API v3 is Enterprise-only. That changed: the current article says Lite and up.

## Which one an agency should buy

**Choose Ahrefs if:**
- Link building and content gap work are most of your SEO retainers.
- You want more API units per dollar for automated reporting (200,000 on Lite vs 50,000).
- Your team is small, so the per-seat cost stays low.

**Choose Semrush if:**
- You sell PPC, local SEO and content in the same retainer and want one vendor for all of it (each extra toolkit is priced on its own).
- Your clients ask how they show up in AI search, and you want that tracking on every plan.
- Account managers who are not SEO specialists need to pull their own reports.

**Use both only if** a client pays for it. Running two suites to settle arguments about whose number is right costs $400+/mo and rarely changes a decision.

## How we use them in Toffu

Toffu connects to Ahrefs directly (domain metrics, keyword rankings and site audits) and to Semrush, or any other tool, through its MCP server: AI Settings → MCP Servers → add the server URL and your API key. Then you ask in plain words, for example "pull every keyword where the client ranks 11 to 30 with 500+ searches and draft the content brief". Toffu calls the tool, works with the rows it gets back, and tells you when the plan blocks a request instead of guessing a number.

[See what Toffu does with Ahrefs](https://toffu.ai/tools/ahrefs) · [Competitor analysis with Toffu](https://toffu.ai/use-cases/competitor-analysis)

## FAQ

**Is Ahrefs cheaper than Semrush?**
At entry level, yes: Ahrefs Lite is $129/mo and Semrush SEO is $139/mo. Ahrefs also has a $29 Starter plan. At 3+ seats the gap depends on the tier, so do the seat math.

**Does Semrush still have Pro, Guru and Business plans?**
Not on the current pricing page. The tiers are SEO, Starter, Pro+ and Advanced. The API docs still refer to "Classic" Pro, Guru and Business plans for existing customers.

**Which tool has better backlink data?**
For link work most practitioners prefer Ahrefs. Test both on domains whose links you know before you commit.

**Can I use Ahrefs or Semrush with ChatGPT, Claude or other AI agents?**
Yes. Both have MCP servers. Ahrefs needs Lite or higher. Semrush needs a plan with API units. Every MCP call uses the same units as a normal API call.
