---
title: "How to Replace Funnel.io With One Nightly Toffu Script"
description: "Copy your ad, analytics and revenue data into your own BigQuery with one Toffu script that runs every night, and stop paying for a data connector."
date: "2026-10-15"
image: "https://raw.githubusercontent.com/toffu-ai/blog-posts/main/images/replace-funnel-io-nightly-script-hero.png"
slug: "replace-funnel-io-with-one-nightly-script"
author: "Toffu"
---

Most agencies pay for a data connector like Funnel.io or Supermetrics for one job: copy ad, analytics and revenue numbers into one place every day, so dashboards and reports can read them. The bill grows with every client and every connector.

Toffu is already connected to those same accounts. So the copy job can be one script that Toffu writes, runs every night, and fixes when it breaks. The tables land in your own warehouse, and you own them.

## What the script replaces

A connector does three things. The script does the same three:

- **Fetch.** Toffu reads each platform through the connections you already have: ad spend and results, analytics sessions and conversions, store revenue. It copies the sources and fields your dashboards use today, not a fixed list.
- **Store.** Rows go into your own BigQuery project, one table per source, each row tagged with the client and the date.
- **Keep current.** An automation runs the script every night and fills any gap.

You do not need to list your clients' accounts anywhere. Toffu already knows which accounts are connected for each client, and reads them from there.

## Rule 1: one script for history and for every night

There is one script, not one per client and not one per source. Loading two years of history is the same script asked for more days. Because history and new data are written the same way, the line between them never shows on a chart.

The script keeps a log: one entry per client, source and day, saying whether that day was written. Each run reads the log and fetches only what is missing. A long history does not fit in one run, so the script stops cleanly when its time is up and the next run picks up where it stopped.

## Rule 2: tables you can re-run safely

New rows are only ever added, never edited or deleted. A view on top of each table shows only the latest complete fetch of each day. So running the same day twice changes nothing on the dashboard, a row the platform no longer reports disappears with the old fetch, and fixing a bad day is just fetching it again.

## Rule 3: dashboards read the tables, not the platforms

Your dashboards, in Looker Studio, another BI tool, or a [Toffu live dashboard](https://toffu.ai/blog/every-number-shows-its-source), read the tables. They load fast, every chart agrees with every other chart, and no job rebuilds pages that nobody opens.

## Three traps the script avoids

Every homemade data pipe hits these sooner or later. The script handles each one from the first night.

**Yesterday stays partial.** A run after midnight sees yesterday before the platforms finish counting it, and platforms keep updating conversions for days. If the script marks that day done, it never fetches it again and the dashboard stays low. So every run fetches the newest few days again, whatever the log says.

**A blank becomes a zero.** A source that is halfway through a refresh can return every date with empty values. Code that turns empty into 0 shows a client with zero revenue, and the number looks real. So an empty value stays empty, the day is not marked done, and the run says which client and source.

**Quiet days look missing.** A day with no ads has no rows, so counting rows would fetch quiet days forever. The log, not the data, decides what is done.

## The part that keeps it running

A connector vendor fixes its own pipes. Here, Toffu does. Every run ends with a short summary: what was written, what was skipped and why, and whether anything is left. When a run fails or a number looks wrong, ask Toffu: it reads that summary and the log, finds the cause, and saves a fixed version of the script. Every version is kept, so any change can be undone.

## Do it for your agency

Toffu has a built-in skill for this, **nightly warehouse ingest**. It holds the rules and the traps above, so you do not have to learn them the hard way. To start:

1. Connect your ad, analytics and store accounts in Toffu, and a BigQuery project.
2. Ask: "Replace our Funnel.io with a nightly script that copies our ad, analytics and revenue data into BigQuery."
3. Toffu asks what your dashboards use today and copies that. It runs one client first and checks the numbers against each platform's own reports. Then it turns on the nightly runs and fills the history.
4. Point your dashboards at the new tables, or ask Toffu for live ones.

Keep your connector running until a full month of numbers matches. Then cancel it.
