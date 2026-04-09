---
name: seo-content-brief
description: Generate a complete SEO content brief for a writer, editor, or content team. Use this skill whenever the user wants to brief a piece of content for SEO, plan a blog post or landing page, define target keywords for a specific page, map content to user intent, specify on-page SEO requirements, or hand off a content assignment to a writer. Also trigger when the user says things like "write me a brief for X", "what should this page cover", "help me plan this article", "I need to brief a writer on this", or "what keywords should this page target."
---

# SEO Content Brief Generator

Produce a complete, writer-ready content brief that serves the user — not the algorithm.

The core principle: a brief should tell a writer *who* they're writing for, *what problem* they're solving, and *what success looks like* — not just a keyword list and a word count. A brief built around user intent produces content that ranks. A brief built around keywords alone produces content that doesn't.

---

## Step 1: Gather inputs

Before writing the brief, collect what's needed. Extract from context if already provided; ask only for what's genuinely missing.

**Required:**
- Topic or working title
- Target URL (new page or existing)
- Primary business goal (traffic, leads, signups, revenue, brand awareness)

**Important:**
- Target persona — who is this page for?
- Funnel stage — awareness / consideration / decision / retention
- Any keyword targets already identified, or starting from scratch?
- Competitors ranking for this topic (if known)
- Existing content on the site that could be internally linked

**Nice to have:**
- Search data from Google Search Console (impressions, existing queries)
- Word count constraints or preferences
- Tone and style guidelines
- Publication deadline

If the user provides a topic and nothing else, make reasonable inferences and state them clearly in the brief. Don't interrogate before delivering value.

---

## Step 2: Define the user and intent

Every brief starts here — not at the keyword.

**Identify the target user:**
Who is searching for this? What's their role, context, and prior knowledge? What problem are they trying to solve right now?

**Classify the search intent:**
- **Informational** — they want to understand something ("how does X work", "what is Y")
- **Navigational** — they're looking for a specific destination ("Ahrefs login", "[Brand] pricing")
- **Commercial** — they're evaluating options ("best X for Y", "X vs Z")
- **Transactional** — they're ready to act ("buy X", "sign up for Y", "download Z")

Intent dictates content format, depth, and CTA. Writing a 3,000-word guide for someone ready to buy wastes their time and yours. Writing a shallow overview for someone early in research loses them before they trust you.

**Map intent to format:**

| Intent + stage | Right format | Wrong format |
|---|---|---|
| Informational / awareness | Long-form guide, explainer, FAQ | Short page, hard sell |
| Commercial / consideration | Comparison, use case, deep review | One-liner landing page |
| Transactional / decision | Landing page, case study, pricing | 2,000-word essay |
| Retention | Tutorial, help doc, feature guide | High-funnel awareness content |

> See [references/intent-formats.md](references/intent-formats.md) for expanded format guidance with examples.

---

## Step 3: Choose and frame keywords

**Primary keyword:** The single query this page is most built to answer. Choose based on user intent first, search volume second. A keyword with 200 monthly searches that exactly matches user intent outperforms one with 2,000 searches that half-fits.

**Secondary keywords:** Related terms and long-tail variants the page should cover naturally. These should emerge from writing for the user — not be stuffed in. List 4–8.

**Semantic terms:** Concepts, entities, and related vocabulary Google expects on a page about this topic. Not keyword targets — signals of topical authority and depth.

**Keyword placement guidance for the writer:**
- Primary keyword in title tag (near the front), H1, and first 100 words of body
- Secondary keywords naturally distributed in H2s and body copy
- Never give the writer a keyword density target — it produces unreadable copy
- One URL = one primary keyword. If two pages compete for the same term, consolidate or differentiate explicitly.

> See [references/keyword-guidance.md](references/keyword-guidance.md) for keyword selection, long-tail strategy, and cannibalization avoidance.

---

## Step 4: Specify on-page SEO requirements

Spell these out explicitly so the writer or editor knows exactly what to produce.

**Title tag**
- 50–65 characters including spaces — truncation after ~65
- Primary keyword near the front
- Unique across the entire site — no two pages with the same title tag
- Written to earn the click, not just to target a keyword — treat it like ad copy

**Meta description**
- 140–160 characters
- Not a ranking factor, but directly drives click-through rate from search results
- Treat it like a micro-ad: describe the page value, signal what the user gets, soft CTA
- Include the primary keyword naturally — search engines bold matched terms

**H1**
- Exactly one per page
- Contains or closely echoes the primary keyword
- Can mirror the title tag or be a slight variation — not required to be identical

**H2 and H3 structure**
- Provide the intended heading hierarchy — this becomes the writer's skeleton
- Each H2 should address a distinct sub-topic or answer a specific user question
- Include secondary keywords in H2s where they fit naturally, not by force

**URL slug**
- Lowercase, hyphen-separated words only
- Short and descriptive — remove stop words (the, a, and, for, of, etc.)
- Keyword in the URL if it fits naturally
- Stable: never change a live URL without a 301 redirect in place

**Image and media requirements (if applicable)**
- Descriptive file names (not IMG_00423.jpg)
- Alt text describes the image and includes a relevant keyword where it fits naturally
- Specify if charts, screenshots, custom graphics, or embedded video are needed

---

## Step 5: Define content structure and depth

This is the most writer-useful part of the brief. Outline what the piece must cover.

**Recommended structure:**
Provide a skeleton of the H2/H3 hierarchy. This isn't a rigid script — it's a scaffold. Good writers improve it.

**Depth and length guidance:**
Length should serve the user's need, not hit an arbitrary word count. Rough guidance:

| Content type | Typical length |
|---|---|
| Comprehensive pillar guide | 2,000–4,000 words |
| Mid-funnel how-to or explainer | 1,000–2,500 words |
| Comparison or review | 1,200–2,500 words |
| Decision-stage landing page | 500–1,000 words |
| Help doc or tutorial | As long as the task requires |
| FAQ page | 800–1,500 words |
| Programmatic / data-driven page | As long as the data fills meaningfully |

**Questions this content must answer:**
List 3–5 specific questions the target user would type into a search bar. The piece is complete when it answers all of them. These become the brief's acceptance criteria.

**What to avoid:**
- Content that duplicates what already exists on the site (cannibalization risk)
- Filler paragraphs that exist to hit a word count, not to help the reader
- Burying the main answer — give the key answer in the first 150–200 words, then expand
- Writing for a keyword instead of a person

---

## Step 6: Internal linking requirements

Internal links distribute authority across the site and guide users deeper. Specify them in the brief — writers who don't know the site won't add them without direction.

**Links this page should receive** (existing pages that should link to this one):
- List 2–5 existing pages that should link here after publication
- Suggest anchor text for each — descriptive, keyword-relevant, not "click here"

**Links this page should give** (outbound internal links to other site pages):
- List 2–5 pages this content should naturally reference
- Note the context in which each link belongs — don't list them without a reason

**Pillar-cluster relationship:**
- Is this a **pillar page** (broad topic hub, links out to cluster pages)?
- Or a **cluster page** (specific sub-topic, links back up to its pillar)?
- State this explicitly — it determines how the writer frames the page's scope and which internal links to prioritize

---

## Step 7: Define the call to action

Every page needs a next step aligned to where the reader is in their journey. Traffic without a CTA is just bounce rate.

| Funnel stage | Appropriate CTA |
|---|---|
| Awareness | Read related guide, subscribe to newsletter, share |
| Consideration | Download resource, start free trial, book a demo |
| Decision | Sign up, buy, contact sales, start free trial |
| Retention | Explore feature, read tutorial, upgrade plan |

The CTA should feel like a natural next step — not an interruption. Match it to where the user is, not just where the business wants them to be.

---

## Brief output format

Produce the brief in this exact structure. Fill every section. Flag assumptions clearly when inputs were incomplete.

```
# Content Brief: [Working Title]

## Overview
- Target URL: [/slug or "new page"]
- Business goal: [traffic / leads / conversions / brand awareness]
- Target persona: [1–2 sentences: who this page is for]
- Funnel stage: [Awareness / Consideration / Decision / Retention]
- Deadline: [if known]

## Search intent
- Primary intent: [Informational / Commercial / Transactional / Navigational]
- What the user is trying to accomplish: [1–2 sentences]
- Why this content satisfies that intent: [1–2 sentences]

## Keywords
- Primary keyword: [keyword] — [est. monthly searches if known]
- Secondary keywords:
  - [keyword 2]
  - [keyword 3]
  - [keyword 4–8]
- Semantic terms to include naturally: [list 6–10 concepts/entities]

## On-page SEO specs
- Title tag: "[Draft — 50–65 characters]"
- Meta description: "[Draft — 140–160 characters]"
- H1: "[Draft]"
- URL slug: /[suggested-slug]

## Content structure
### [H2: Section 1 title]
- [Key points or sub-questions to address]
- [H3 if needed]

### [H2: Section 2 title]
- [Key points]

### [H2: Section 3–6...]

## Questions this content must answer
1. [User question 1]
2. [User question 2]
3. [User question 3]
4. [User question 4 — optional]
5. [User question 5 — optional]

## Depth and format
- Target length: [X–Y words]
- Format: [guide / comparison / tutorial / landing page / FAQ / etc.]
- Tone: [informational / conversational / authoritative / persuasive]
- Required elements: [data, screenshots, examples, embed, etc.]

## Internal linking
### This page should receive links from:
- [Page title — /url] — anchor: "[suggested anchor text]"

### This page should link to:
- [Page title — /url] — context: [when / why to link]
- Pillar/cluster: [Is this a pillar or cluster? Link to pillar: /url]

## Call to action
- Primary CTA: [action + copy direction]
- Placement: [Top / Mid / Bottom / All three]
- Secondary CTA (optional): [if applicable]

## What NOT to cover
[Scope limits — topics handled elsewhere, avoid duplication]

## Success metric
- Primary measure of success: [organic sessions / leads / conversions / etc.]
- Review date: [when to evaluate page performance]
```
