---
title: "Google Analytics Traffic Analysis: How to Check and Read Your Website Traffic in GA4"
seoTitle: "Google Analytics Traffic Analysis: Check Website Traffic"
description: "How to check website traffic in Google Analytics 4, which reports to open, and how to spot fake traffic. With a worked analysis of Google's public GA4 store data."
date: "2025-10-03"
image: "https://raw.githubusercontent.com/toffu-ai/blog-posts/main/images/google-analytics-traffic-analysis-hero.png"
slug: "google-analytics-traffic-analysis"
author: "Toffu Team"
---

*Updated 16 November 2026.*

To check your website traffic in Google Analytics 4, open **Reports → Acquisition → Traffic acquisition**. It shows sessions by channel (Organic Search, Direct, Paid, Social and more), with engagement and key events next to each one. Set the date range at the top right and turn on **Compare** to see the change against the previous period.

That gives you the numbers. The harder part is knowing which numbers are real. We ran the full analysis on Google's own public GA4 data: **sessions grew 22% in a month, but real traffic grew less than 5%**. The breakdown is below, and the method works on any site.

## The 3 reports that answer most traffic questions

| Question | Report in GA4 | What to look at |
|---|---|---|
| How much traffic did we get, and from where? | Reports → Acquisition → **Traffic acquisition** | Sessions and engagement rate by "Session primary channel group" |
| Which channels bring *new* people? | Reports → Acquisition → **User acquisition** | New users by "First user primary channel group" |
| Which pages do people land on? | Reports → Engagement → **Landing page** | Sessions, engagement rate and key events per landing page |

Traffic acquisition counts every session. User acquisition credits each user to the channel that first brought them. When the two disagree, for example Organic Search brings many new users but few sessions, you learn which channel finds people and which one brings them back.

If you only want a quick daily check, **Reports → Realtime** shows the last 30 minutes. It is useful to confirm that tracking works. It is useless for analysis.

## The 4 numbers to read, in this order

1. **Sessions.** One visit. One person can make many.
2. **Engagement rate.** The share of sessions that lasted more than 10 seconds, viewed 2+ pages, or triggered a key event. It replaced bounce rate as the main quality signal. Bounce rate in GA4 is simply 100% minus engagement rate.
3. **Average engagement time per session.** The time the page was in the foreground. It is more honest than the old "time on site".
4. **Key events per session.** Key events are the actions you marked as important (sign-ups, demo requests, purchases). Google renamed "conversions" to "key events" in 2024.

Read them per channel and per landing page, never as one sitewide average. A sitewide average hides the problem you are looking for.

## A worked example: the Google Merchandise Store

Google publishes real GA4 data from its own online store as a [public BigQuery dataset](https://developers.google.com/analytics/bigquery/web-ecommerce-demo-dataset). Anyone can query it, so you can check every number below. We compared 1 to 28 December 2020 with 3 to 30 November 2020, the same 28-day length.

Google obfuscates part of the dataset, so some sources show as "<Other>" or "(data deleted)". We keep those as their own row instead of guessing.

**Topline:** 124,084 sessions against 102,060, **+22%**. Purchases +18%. A good month, at first sight.

**By channel (December)**

| Channel | Sessions | Change vs Nov | Avg engagement time | Purchases per 100 sessions |
|---|---|---|---|---|
| Organic Search | 34,504 | +25% | 93s | 2.34 |
| No source recorded | 31,000 | +44% | 8s | 0.00 |
| Referral from the store's own domain | 19,639 | +5% | 124s | 3.38 |
| Direct | 14,474 | +16% | 76s | 1.17 |
| Obfuscated by Google | 12,086 | +16% | 78s | 1.37 |
| Referral (other sites) | 9,120 | +8% | 146s | 5.53 |
| Paid Search | 2,991 | +19% | 64s | 0.87 |

**By landing page (December, top 5)**

| Landing page | Sessions | Avg engagement time | Purchases per 100 sessions |
|---|---|---|---|
| / (home) | 47,814 | 116s | 2.58 |
| /Google+Redesign/Apparel | 15,587 | 28s | 0.41 |
| /Google+Redesign/Apparel/Google+Dino+Game+Tee | 9,827 | 6s | 0.01 |
| (not set) | 8,951 | 8s | 0.00 |
| /Google+Redesign/Shop+by+Brand/YouTube | 8,514 | 47s | 0.38 |

The two tables show three problems that the topline hides.

**1. One product page went from 30 to 550 sessions a day overnight.** The Dino Game Tee page got about 30 landing sessions a day in November. From 4 December it got 400 to 600 a day on weekdays. The new sessions came from every channel at once, lasted 6 seconds, and produced 1 purchase in 9,827 sessions. A real promotion brings people who look at the product. This is a pattern to investigate (a link placed somewhere unusual, a crawler, or a tag firing on a preview) before anyone reports it as growth.

**2. A quarter of all sessions have no source.** 31,000 sessions carry no source or medium at all. They average 8 seconds and produced zero purchases. This group grew 44%, twice as fast as the site.

**3. The store refers traffic to itself.** 16% of sessions are credited to a referral from the store's own domain, and those sessions made 28% of all purchases. That is a classic cross-domain or self-referral setup error: the visitor came from somewhere real, and GA4 lost it when they crossed between hostnames. Every one of those buyers is credited to the wrong channel.

Remove the Dino Tee spike and the no-source sessions, and sessions grew from 79,738 to 83,417: **+4.6%, not +22%**. Purchases still grew 18%. So the real story of December was better conversion during the holiday season, not more traffic. That is a different report, and a different decision about where to spend.

## How to find fake or broken traffic in your own GA4

Run these checks every month before you report a number to anyone:

1. **Landing page = (not set) over 5% of sessions?** Look at it. Add a secondary dimension of **Hostname**. Traffic on hostnames that aren't yours is spam or a copied tag.
2. **Direct share jumped?** Break Direct down by **Country** and **Device category**. A spike from one country on one device type is rarely human.
3. **Engagement rate under 20% on a whole channel?** Real visitors engage more than that. Check that channel by source.
4. **Check the tag.** In Google Tag Manager preview mode, load your site and confirm a `page_view` fires on every page, including pages that change without a full reload (single-page apps).
5. **Filter internal traffic.** Admin → Data streams → Configure tag settings → Define internal traffic, then turn the filter on in Data filters.

Until you fix the cause, report conversion rates on traffic **with landing page not equal to (not set)**. In Explorations, add that as a filter. Your numbers will be smaller and true.

## Reading the channels

- **Organic Search** is people who found you on Google or Bing. Pair GA4 with Search Console to see the queries. GA4 doesn't show them.
- **Direct** is "we don't know". Typed URLs and bookmarks, but also links from apps, PDFs, email clients that strip the referrer, and bots. A big Direct share is a measurement question before it is a marketing one.
- **Unassigned** is traffic GA4 can't fit into any channel rule, usually because of missing or odd UTM parameters. If it is above a few percent, check your UTM naming.
- **AI Assistant** is visits from ChatGPT, Perplexity, Gemini and similar tools. It is small for most sites, but it grows fast. Watch its trend.
- **Paid Search / Paid Social** should match the clicks in your ad platforms within a reasonable margin. A big gap means broken UTMs or a landing page that loads slowly.

## Diagnosing a traffic drop in 5 minutes

1. **Is it everywhere or in one channel?** Traffic acquisition, compare to the previous period, sort by change.
2. **Is it one landing page?** Landing page report, same comparison.
3. **Is it real?** If the drop is in Organic Search, check Search Console for the same dates. If Search Console is flat, the problem is tracking, not rankings.
4. **Did something change?** A site release, a consent banner, a tag change or a paused campaign explains most drops.

## Doing this without the clicking

The checks above take a few report changes and a comparison. [Toffu](https://toffu.ai/tools/google_analytics) connects to your GA4 property and runs them when you ask in plain words, for example "compare this month's traffic by channel and landing page with last month and tell me what's real". It pulls the reports, compares the periods, and flags spikes like the Dino Tee page or a self-referral before you report a number. [See what Toffu does with Google Analytics](https://toffu.ai/tools/google_analytics).

## FAQ

**How do I check website traffic in Google Analytics?**
Reports → Acquisition → Traffic acquisition. Set the date range and turn on Compare.

**What does "(not set)" mean as a landing page?**
GA4 recorded the session but no page view with it, so it can't name a landing page. Common causes are bots, sessions that start with a non-page event, and broken tagging.

**What is a good engagement rate?**
It depends on the page type. Look at the trend and compare channels with each other. A channel far below the rest, or under 20%, needs a check.

**Why does my own domain show up as a referral?**
Usually a cross-domain setup error: the visitor moves between two of your hostnames (for example the shop and the checkout) and GA4 starts a new session. Add both domains under Admin → Data streams → Configure tag settings → Configure your domains, and list your own domains under unwanted referrals.

**Why is my Direct traffic so high?**
Direct collects every visit without a referrer: typed URLs, bookmarks, apps, some email clients, and bots. Break it down by country, device and landing page before you trust it.
