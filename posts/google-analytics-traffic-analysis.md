---
title: "Google Analytics Traffic Analysis: How to Check and Read Your Website Traffic in GA4"
seoTitle: "Google Analytics Traffic Analysis: Check Website Traffic"
description: "How to check website traffic in Google Analytics 4, which reports to open, and how to spot fake traffic. With a real analysis of our own site."
date: "2025-10-03"
image: "https://raw.githubusercontent.com/toffu-ai/blog-posts/main/images/google-analytics-traffic-analysis-hero.png"
slug: "google-analytics-traffic-analysis"
author: "Toffu Team"
---

*Updated 16 November 2026.*

To check your website traffic in Google Analytics 4, open **Reports → Acquisition → Traffic acquisition**. It shows sessions by channel (Organic Search, Direct, Paid, Social and more), with engagement and key events next to each one. Set the date range at the top right and turn on **Compare** to see the change against the previous period.

That gives you the numbers. The harder part is knowing which numbers are real. When we ran this analysis on our own site, **more than half of our sessions turned out to be noise**. The full breakdown is below, and the method works on any site.

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

## A real example: our own site, last 28 days

We asked [Toffu](https://toffu.ai/tools/google_analytics) to run exactly this analysis on toffu.ai on 16 November 2026: 19 Oct to 15 Nov 2026, compared with the 28 days before. We show shares and percentage changes, not raw counts.

**By channel**

| Channel | Share of sessions | Previous period | Sessions change | Engagement rate | Avg engagement time |
|---|---|---|---|---|---|
| Direct | 61.5% | 44.9% | +85% | 53.4% | 167s |
| Organic Social | 11.6% | 10.2% | +53% | 59.7% | 341s |
| Organic Search | 10.0% | 9.3% | +46% | 59.3% | 151s |
| Unassigned | 7.9% | 23.1% | −54% | 7.8% | 189s |
| Referral | 5.0% | 5.1% | +30% | 71.0% | 218s |
| AI Assistant | 2.1% | 1.5% | +88% | 65.4% | 69s |

Smaller channels (paid, shopping, video, email) are left out.

**By landing page (top 5)**

| Landing page | Share of sessions | Engagement rate | Key events per session |
|---|---|---|---|
| (not set) | 51.5% | 25.8% | 0.001 |
| / (home) | 12.4% | 77.6% | 0.080 |
| /account/login | 0.7% | 57.7% | 0.036 |
| /clients | 0.6% | 83.2% | 0.264 |
| /tools/facebook | 0.5% | 71.7% | 0.292 |

At first sight, total sessions were up about 35%. Then the landing-page table shows the real story.

**51.5% of sessions have no landing page.** Those sessions engage 26% of the time and almost never convert (0.001 key events per session). Real pages convert 80 to 290 times better. The same group doubled against the previous period. At the same time Direct jumped from 45% to 62% of all sessions.

When Direct and "(not set)" grow together and engagement is low, it is almost always one of two things:

- **Bots or automated traffic** that runs your tag without loading a page normally.
- **Broken tagging:** hits that arrive without a `page_view` event, so GA4 can't assign a landing page.

Our 35% growth was mostly noise. The real pages (home, pricing, tool pages) were flat or down. Without the landing-page check we would have reported a great month.

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
- **AI Assistant** is visits from ChatGPT, Perplexity, Gemini and similar tools. It is small for most sites, but on ours it grew 88% in one period and engages better than Direct. Watch its trend.
- **Paid Search / Paid Social** should match the clicks in your ad platforms within a reasonable margin. A big gap means broken UTMs or a landing page that loads slowly.

## Diagnosing a traffic drop in 5 minutes

1. **Is it everywhere or in one channel?** Traffic acquisition, compare to the previous period, sort by change.
2. **Is it one landing page?** Landing page report, same comparison.
3. **Is it real?** If the drop is in Organic Search, check Search Console for the same dates. If Search Console is flat, the problem is tracking, not rankings.
4. **Did something change?** A site release, a consent banner, a tag change or a paused campaign explains most drops.

## Doing this without the clicking

The analysis above took Toffu under a minute: it pulled the channel and landing-page reports from GA4, compared the two periods, and flagged the "(not set)" problem on its own. You can ask the same in plain words, for example "compare this month's traffic by channel and landing page with last month and tell me what's real". [See what Toffu does with Google Analytics](https://toffu.ai/tools/google_analytics).

## FAQ

**How do I check website traffic in Google Analytics?**
Reports → Acquisition → Traffic acquisition. Set the date range and turn on Compare.

**What does "(not set)" mean as a landing page?**
GA4 recorded the session but no page view with it, so it can't name a landing page. Common causes are bots, sessions that start with a non-page event, and broken tagging.

**What is a good engagement rate?**
It depends on the page type. Look at the trend and compare channels with each other. A channel far below the rest, or under 20%, needs a check.

**Why is my Direct traffic so high?**
Direct collects every visit without a referrer: typed URLs, bookmarks, apps, some email clients, and bots. Break it down by country, device and landing page before you trust it.
