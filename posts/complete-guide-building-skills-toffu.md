---
title: "The Complete Guide to Building Skills in Toffu (2026)"
description: "Skills are the fastest way to make Toffu work the way your team actually works - without re-explaining your context in every conversation. Here's how to build them well."
date: "2026-03-10"
image: "https://raw.githubusercontent.com/toffu-ai/blog-posts/main/images/complete-guide-building-skills-toffu-hero.png"
slug: "complete-guide-building-skills-toffu"
---

# The Complete Guide to Building Skills in Toffu (2026)

Skills are the fastest way to make Toffu work the way your team actually works - without re-explaining your context in every conversation.

This guide covers what skills are, when to use them instead of playbooks, how to build them well, and patterns that work across different use cases.

---

## What Is a Skill?

A skill is a block of expertise or context that Toffu applies automatically in every conversation. Once saved, you don't trigger it - it runs in the background, shaping how Toffu thinks and responds without you having to mention it.

The contrast with playbooks makes this concrete:

| | Skills | Playbooks |
|:---|:---|:---|
| What it is | Background knowledge | Step-by-step workflow |
| When it applies | Every conversation | When you run it |
| How to use | Set it and forget it | Trigger on demand |
| Best for | Context, rules, expertise | Repeatable tasks |

A skill answers: "What should Toffu always know or always do?"

A playbook answers: "What steps should Toffu follow to complete this specific task?"

---

## When to Build a Skill

Build a skill when you find yourself correcting Toffu in the same way more than once.

Concrete triggers:

- You explain your brand voice at the start of every content session
- You tell Toffu your target audience every time you ask for copy
- You repeat the same competitive framing in every analysis
- You specify the same report structure in every request
- You always exclude the same channels, tools, or approaches from suggestions

If you're re-explaining something, it belongs in a skill.

**Use a skill for:**
- Brand voice and writing rules
- Target audience definition
- Competitive context (who your main competitors are, how to treat them)
- Report or output formats your team uses
- Channel constraints (what you do and don't run)
- Domain knowledge specific to your business or industry
- Rules about how Toffu should escalate, flag, or ask for clarification

**Use a [playbook](https://toffu.ai/playbooks) instead for:**
- A weekly SEO post workflow
- A competitor ad monitoring process
- A Google Ads optimization audit
- Any multi-step task you run on a schedule or trigger manually

---

## The 3 Types of Skills Worth Building First

### 1. Brand Voice

The most universally useful skill. Without it, every piece of content Toffu writes defaults to generic AI tone - functional but not yours.

A good brand voice skill covers:
- Sentence length and structure
- Words and phrases to avoid
- Tone (dry, warm, direct, technical, etc.)
- How to open content (what to lead with and what not to)
- Platform-specific rules if your voice differs across channels

**Example:**

> Write in a direct, conversational tone. Short sentences. Active voice. Never use: leverage, synergy, streamline, best-in-class, cutting-edge, robust, "it goes without saying", "in today's fast-paced world".
>
> Lead with the concrete problem or benefit - not with the company name or product. No exclamation marks except in truly exceptional cases. Contractions encouraged. Write like you're explaining something to a smart colleague, not presenting to a board.
>
> On LinkedIn: text-native format, line breaks between every 1-2 sentences, end with a question. No link-in-post - always put links in comments.

### 2. Target Audience

Without this, Toffu writes for a generic "user" rather than your specific ICP. This affects copy angle, examples, objections addressed, and proof points used.

A good audience skill covers:
- Job title and seniority of primary buyer
- Company size and stage
- What they're measured on
- Their biggest pain points
- What makes them skeptical
- Who you don't sell to (equally important)

**Example:**

> Primary buyers: Heads of Marketing and VP Marketing at B2B SaaS, 50-500 employees. Measured on pipeline and revenue, not vanity metrics. Skeptical of AI hype - respond to specifics and ROI numbers, not abstract promises.
>
> Secondary: marketing managers doing hands-on execution. They care about time savings and ease of use.
>
> We don't sell to enterprise (500+) or SMBs under 20 employees. Flag if content targets those segments.
>
> Pain points that resonate: too many tools, disconnected data, pressure to show ROI, content bottlenecks, difficulty scaling without headcount.

### 3. Competitor Context

For any competitive analysis, ad research, or positioning work, Toffu needs to know who your actual competitors are and how to think about them.

A good competitor skill covers:
- Who your main direct competitors are
- Any rules about how to treat them (always cite sources, never invent data)
- What categories of competitor to include vs. exclude
- Any known differentiators to highlight

**Example:**

> Main direct competitors: Jasper, Copy.ai, Writer. Treat these as the baseline in any competitive analysis.
>
> When analyzing a competitor: cover positioning, pricing, content strategy, recent launches, and weaknesses - in that order. Always cite sources. If information is unclear or unavailable, say so - don't fill gaps with assumptions.
>
> We differentiate on task execution, not content generation. Toffu does work; the others generate text. Highlight this distinction when relevant.

---

## The Easiest Way to Build Skills: Extract from Conversation

The fastest path to a useful skill is to run a real task, correct what's wrong, then ask Toffu to turn those corrections into a skill.

**How it works:**

1. Start a chat and work on something real - a LinkedIn post, an analysis, a report
2. When Toffu gets something wrong, correct it
3. When it gets something right, note what worked
4. At the end, ask Toffu to turn those preferences into a skill

**Example:**

> You: Write a LinkedIn post about our new HubSpot integration.
>
> Toffu: [writes a formal announcement post]
>
> You: Too formal. We don't lead with announcements - we lead with the problem it solves. Shorter, no exclamation marks, no "we're thrilled to announce."
>
> Toffu: [rewrites]
>
> You: Better. Always end with a question to drive comments.
>
> Toffu: [rewrites again]
>
> You: That's it. Turn what you've learned into a skill I can save.

The skill Toffu produces reflects how you actually work, not a set of rules you wrote in advance and forgot about.

**Prompts to extract a skill from a session:**
- "Turn the feedback I just gave you into a skill I can save"
- "Based on this conversation, what skill would mean you don't need correcting next time?"
- "Write a skill that captures how we've been working in this chat"
- "What rules have I applied in this session? Write them up as a skill."

---

## Creating Skills Manually

Go to **Skills** in the sidebar. Click **Create Skill** and fill in:

- **Name** - A short label (e.g. "Brand Voice", "Report Format", "Audience")
- **Description** - What this skill does (shown in the skills list)
- **Content** - The actual instructions or knowledge
- **Scope** - Personal (just you), Team, or Company (applies to everyone automatically)

**Scope matters.** If your brand voice applies to everyone on the team, set it to Company. If it's a personal working style preference, keep it Personal. Team and Company skills are automatically active for anyone in that scope - they don't need to enable them.

---

## Writing Effective Skill Content

**Be specific, not generic.** The more specific the skill, the more useful it is. "Write in a professional tone" teaches Toffu nothing. "Write in short, direct sentences. No bullet points in LinkedIn posts. Never use the word 'leverage'." teaches it something it can actually apply.

**Include examples where possible.** Showing what good output looks like is more effective than describing it. Include a sentence like "Here's an example of the tone we use:" followed by a real sample.

**Include what to avoid.** Negative rules are often more useful than positive ones. "Don't use X" is clearer than "use Y instead."

**Use a few sentences to a few paragraphs.** Too short means too vague. Too long means Toffu has to prioritize and may miss things. A skill between 100-400 words is usually the right range.

**Test it by running a real task.** After saving, run the type of task the skill is meant to improve. Check whether the output reflects the skill. If not, iterate - add examples, tighten the rules, remove anything ambiguous.

---

## Skill Patterns by Use Case

### Content and Copy

Skills that improve every piece of content Toffu writes:

- **Brand voice** - tone, structure, words to avoid, platform-specific rules
- **Messaging framework** - what problem you solve, how you position against alternatives, proof points to use
- **Content rules** - what content formats to use, what topics are in/out of scope, how to handle CTAs

### Campaign and Performance

Skills that improve ad copy, campaign briefs, and performance analysis:

- **Campaign structure rules** - how you name campaigns, how you organize ad groups, naming conventions
- **ICP for ads** - who the ads target, what pain points to hit, what social proof matters to them
- **Performance thresholds** - what CTR, CPA, and ROAS you consider acceptable vs. flagged

### Analysis and Reporting

Skills that ensure every report Toffu produces matches your format:

- **Report format** - structure, header levels, summary format, how many recommendations, length
- **Data sources** - which sources to trust, which to treat as estimates, what to always cross-reference
- **Escalation rules** - when to flag something vs. just report it

---

## Skills vs. Playbooks: The Practical Distinction

The simplest test: if you'd want this applied to a one-off question, it's a skill. If you'd only want it when you're running a specific process, it's a playbook.

You want Toffu to always write in your brand voice - even when you ask a quick question. That's a skill.

You want Toffu to run a 5-step Google Ads audit every Monday morning. That's a [playbook](https://toffu.ai/playbooks/google-ads-optimization).

Most teams need both. Skills handle the context that makes everything Toffu does feel like yours. Playbooks handle the recurring workflows you want to run consistently and on demand. The [Playbooks Library](https://toffu.ai/playbooks) has pre-built workflows for the most common marketing tasks - most teams start there and add custom skills around them.

---

## Building Your Skill Library Over Time

Start with the three highest-leverage skills:

**Week 1:** Brand voice. Run a content task, correct what's wrong, extract into a skill. This improves every piece of content from that point forward.

**Week 2:** Target audience. Define your ICP precisely - job title, company size, pain points, who you don't sell to. This sharpens every piece of copy and every outreach message.

**Week 3:** Competitor context. List your main competitors and how to think about them. This makes every competitive analysis and positioning task faster and more accurate.

After those three, add skills based on what you keep correcting. Every correction is a signal that a skill is missing. The goal is a library where Toffu runs like a teammate who's been onboarded properly - not one you have to re-brief every session.

See the full skills reference at [toffu.ai/academy/skills](https://toffu.ai/academy/skills).