---
name: seo-stakeholder-pitch
description: Build a compelling SEO pitch for executives, leadership, or cross-functional teams. Use this skill whenever the user needs to get buy-in for SEO investment, justify an SEO budget, request engineering or product resources for SEO, present SEO strategy to a CEO/CMO/CFO, prepare for annual or quarterly planning, convince a skeptical stakeholder that SEO is worth prioritizing, or translate SEO into business language. Also trigger when the user says things like "my boss doesn't get SEO", "how do I sell this internally", "I need to pitch this to leadership", or "nobody is taking SEO seriously here."
---

# SEO Stakeholder Pitch Builder

Help the user build a pitch that gets SEO resourced, funded, and prioritized — by translating it out of SEO jargon and into the language executives actually use.

The core insight: SEO pitches fail not because SEO doesn't work, but because they're framed wrong. Executives don't care about rankings, backlinks, or domain authority. They care about revenue, growth, and competitive position. The pitch must speak their language.

---

## Step 1: Diagnose the situation

Before writing anything, understand who the pitch is for and what's blocking SEO investment. Ask if not already clear:

**Audience**
- Who is being pitched? (CEO, CMO, CFO, VP Product, Engineering lead, board)
- What do they care most about? (Revenue growth, cost efficiency, competitive moats, risk reduction)
- Have they funded SEO before? What was their experience?

**Current state**
- Is there existing SEO investment, or is this a new ask?
- Are there results/data to point to, or is this a zero-baseline pitch?
- What's the specific ask? (Headcount, engineering time, content budget, tool licenses, a new initiative)

**The blocker**
- Why hasn't this been funded/prioritized already?
- Is it skepticism ("SEO doesn't work for us"), competing priorities, unclear ROI, or just never been asked properly?

> See [references/audience-profiles.md](references/audience-profiles.md) for tailored framing by executive type.

---

## Step 2: Build the business case

A strong SEO pitch has four components. Build all four before writing the pitch itself.

### 1. The opportunity number
Translate the SEO opportunity into a revenue or growth figure. Never pitch "we could rank for these keywords." Pitch "there are X monthly searches for problems our product solves, and we're capturing less than Y% of that."

To estimate the opportunity:
- Use Google Search Console impression data (most credible — straight from Google)
- Use competitor traffic estimates as a proxy (SimilarWeb, Ahrefs, Semrush)
- Use a tangential market's traffic as a proxy if starting from zero
- Apply a realistic CTR (3–5% for position 3–5, 10–15% for position 1–2) and current conversion rate

Example framing:
> "Our top 3 competitors combined receive an estimated 400,000 monthly organic visits for queries directly relevant to our product. We receive 12,000. Closing even 20% of that gap is worth approximately $X in pipeline at our current conversion rate."

**Never use keyword volume alone as the opportunity number.** It doesn't translate to business impact and executives will ask "so what?"

### 2. The cost comparison
Contextualize SEO investment against what the business is already spending on paid acquisition.

> "We currently spend $X/month on paid search to acquire Y customers. Those customers stop coming the moment we stop paying. The same SEO investment, made once, compounds — traffic earned stays earned."

SEO is owning; paid is renting. Use that framing explicitly if the audience thinks in terms of CAC.

### 3. The competitive case
Identify 1–2 direct competitors winning organically. Show what they've built and what it's worth to them. This is often the most persuasive data point for executives — they don't want to be left behind.

> "Competitor X receives an estimated 200,000 monthly organic visits. At even a 1% conversion rate and a $500 ACV, that's $1M/month in organic-influenced revenue — from a channel they invested in 3 years ago."

### 4. The specific ask, scoped tightly
Never pitch "we need to do SEO." Pitch a specific, bounded initiative with a defined output and timeline.

Good pitch structure: *"I'm asking for [X resource] to [build Y specific thing] by [date], which will [deliver Z measurable outcome] within [timeframe]."*

Bad: "We need more SEO investment."
Good: "I'm asking for one engineer for 6 weeks to build programmatic city landing pages. Based on search demand, this should generate 15,000 additional monthly organic visits within 6 months, worth approximately $X in pipeline."

---

## Step 3: Translate SEO into their language

Strip all SEO jargon from the pitch. Replace every technical term with a business equivalent.

| Never say | Say instead |
|---|---|
| "We need more backlinks" | "We need to build domain credibility so we're trusted by search engines — here's how we earn that through content" |
| "Our domain authority is low" | "Our organic credibility relative to competitors is a gap. Here's the 6-month plan to close it." |
| "We need to fix our title tags and meta descriptions" | "40 of our highest-traffic pages are invisible in search — this is a 2-day fix with estimated X monthly visits recovered" |
| "We should target these keywords" | "There are 50,000 monthly searches for the exact problems our product solves — we're not showing up for any of them" |
| "Our bounce rate is high" | "Organic visitors who land on these pages are leaving without converting — here's why and what to fix" |
| "We need to improve Core Web Vitals" | "Our pages load too slowly for Google to rank them competitively — here's the engineering fix" |
| "We need a content calendar" | "We need a production plan to publish the 30 pages that will capture X monthly organic visits" |
| "DA/DR score" | Never mention this to executives |
| "Crawl budget" | "Google isn't seeing our most important pages — here's what to fix" |
| "Canonical issues" | "We have duplicate content confusing search engines — this is suppressing our rankings across 200 pages" |

---

## Step 4: Frame SEO as a product, not a campaign

One of the biggest reasons SEO loses budget battles: it's framed as a marketing campaign (ongoing spend, fuzzy ROI) rather than a product (one-time build, compounding return).

Reframe accordingly:

> "This isn't a campaign. We're building an acquisition channel. Like any product, it requires upfront investment in engineering, design, and content — and like any product, once it's built, it generates compounding returns without ongoing spend proportional to output."

This framing matters most when pitching to:
- **CFOs** — they understand asset vs. expense; SEO as an asset is a much easier sell
- **Product teams** — they understand roadmap investment; pitch it as a product workstream, not a marketing ask
- **CEOs** — they understand moats; pitch SEO as a defensible acquisition channel competitors can't easily copy

---

## Step 5: Handle objections

Pre-empt the most common executive objections with data and reframes.

> See [references/objection-handling.md](references/objection-handling.md) for full objection scripts.

**"SEO takes too long"**
> "You're right that SEO isn't instant — typically 6–12 months to see compounding results. That's exactly why we should start now. Every month we wait is a month our competitors extend their organic lead. Paid delivers instantly but stops the moment spend stops. SEO compounds — the work we do today pays off for years."

**"We tried SEO before and it didn't work"**
> "What you tried before was [keyword-focused content / agency-driven link building / etc.]. What I'm proposing is different — it's building a product that users want to find, then making sure search engines can find it. The companies winning organically aren't doing traditional SEO. They're building for users first."

**"How do we know this will work?"**
> "We can derisk this with a 90-day pilot. Here's the specific initiative, the success metric we'll track, and the checkpoint where we decide whether to continue. The downside is bounded — [X hours of engineering, $Y in content]. The upside is [estimate]."

**"We don't have the engineering resources"**
> "I've scoped this to require [X] engineering hours. Here are 3 tiers of this initiative — a version we can do with no engineering, a version with 2 weeks of engineering time, and the full version. The no-engineering version still moves the needle by [estimate]."

**"Paid search works better for us"**
> "Paid and organic are complementary, not competitive. Paid gives us immediate, targeted reach. Organic gives us durable, compounding reach. The highest-performing acquisition programs use both. Right now we're 100% reliant on paid, which means our acquisition stops if spend stops. SEO is the hedge."

---

## Step 6: Structure the pitch document

Use this structure for a written deck or memo. Adapt length to audience — a CEO gets a 1-pager; a planning document gets full detail.

```
## SEO Investment Proposal: [Initiative Name]

### The opportunity (1 paragraph)
[Quantified search opportunity in revenue/pipeline terms. No SEO jargon.]

### Where we stand vs. competitors (1 paragraph + 1 data point)
[Specific competitor doing well organically + estimated value of their organic channel.]

### What we're building (2–3 sentences)
[Specific initiative. What gets built. What it does for users.]

### The ask
- Resource: [Headcount / engineering time / budget]
- Timeline: [Start → milestone → outcome date]
- Cost: [$X or X engineering-weeks]

### Expected return
- Traffic: [X monthly organic visits within Y months]
- Pipeline/revenue impact: [$X at current conversion rate]
- Payback period: [When the channel pays for itself]

### How we'll measure success
- Primary metric: [Organic sessions / leads / revenue]
- 90-day checkpoint: [Specific milestone]

### What happens if we don't do this
[Competitor advantage, continued paid dependency, growing gap to close later]
```

---

## Pitch variations by context

Different situations need different emphasis. Use the right frame:

**Annual / quarterly planning pitch** — Emphasize that resources denied now = a year lost. Use the "losing at planning" frame: teams that don't win resources are deprioritized for 12 months. Make the downside of inaction concrete.

**New SEO initiative pitch** — Lead with the opportunity number. Show a scoped pilot with a bounded downside. Make the ask small enough to say yes to.

**Rescuing a stalled SEO program** — Acknowledge what didn't work before. Show clearly why this is different. Use a before/after framing: "what we did before" vs. "what product-led SEO looks like."

**Pitching to a skeptical engineer or product lead** — Don't sell SEO. Sell the user problem. "There are 50,000 people a month searching for X and landing on garbage. We can build something genuinely better. SEO is just how they'll find it."

**Pitching SEO as headcount** — Frame around throughput, not expertise. "Without a dedicated SEO PM, every request has to fight for prioritization against product features. A dedicated person means [X initiatives] per quarter instead of 1."

> See [references/pitch-templates.md](references/pitch-templates.md) for copy-paste pitch templates by scenario.

---

## What not to do

These are the most common ways SEO pitches fail — flag them if they appear in the user's draft:

- **Leading with rankings** — rankings are a vanity metric, not a business outcome. Cut them.
- **Using SEO acronyms (DA, DR, CTR, SERP) without explaining them** — executives don't know these and won't ask; they'll just disengage.
- **Vague asks ("we need more SEO investment")** — always ask for something specific and bounded.
- **Pitching against paid instead of alongside it** — frame as complementary, not competitive.
- **Using keyword tool volume as the opportunity** — tool estimates are guesses. Google Search Console data and competitor traffic estimates are more credible.
- **Projecting hockey-stick growth without a basis** — if you can't justify the number with data, don't use it. Credibility > ambition.
- **Skipping the "what if we don't?" section** — inaction has a cost. Make it explicit.
