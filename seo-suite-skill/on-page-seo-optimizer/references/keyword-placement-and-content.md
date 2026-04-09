# Keyword Placement & Content Quality Reference

*Sourced from: The Art of SEO — Enge, Spencer, Fishkin & Stricchiola (Ch. 6: Developing an SEO-Friendly Website)*

---

## Keyword Placement Priority Hierarchy

Place the primary keyword in these locations, in descending order of ranking importance:

```
1. Title tag                    ← Highest weight; most critical element
2. H1 heading tag               ← Second most important signal
3. First 100 words of body      ← Early placement signals topical focus
4. At least one H2 heading      ← Reinforces topic across section structure
5. Image alt attributes         ← Where images are directly relevant to keyword
6. Throughout body text         ← Naturally, 2–5x per 500 words
7. URL slug                     ← Lower weight but supports the full signal picture
8. Meta description             ← CTR signal, not ranking signal
```

**Consistency rule:** All signals should reinforce the same topic. A page where the title says "cordless drills," the H1 says "power tools," and the body content is mostly about "home improvement" will rank poorly because the signals contradict each other.

---

## Keyword Density — What the Numbers Actually Mean

"Keyword density" as a target metric is obsolete. Here is what the evidence actually supports:

| Claim | Reality |
|---|---|
| "Aim for 2–3% keyword density" | No evidence this threshold has ranking value |
| "More uses = higher ranking" | False beyond basic inclusion. Testing shows even one low-quality link outweighs perfect keyword saturation |
| "Keyword stuffing helps" | Penalized. Engines recognize it as a disingenuous tactic |
| "The keyword must appear at least once" | **True** — a page that never uses the target phrase will almost never rank for it |
| "2–10 natural uses in 500-word content is enough" | **True** — supported by testing |
| "Related terms and synonyms matter" | **True** — semantic context around the keyword strengthens relevance |

**Practical instruction:** Use the target keyword in the title, H1, and first paragraph. Then write naturally — if the keyword appears 3–8 more times in a 1,000-word piece, that's appropriate. Do not count.

---

## Semantic Context: Building Topical Relevance

Search engines build vocabulary models of what concepts co-occur with each topic. A page is more likely to rank when it covers the semantic neighborhood of the target keyword, not just the exact phrase.

### How to identify related terms

1. Search your target keyword in Google
2. Look at the "People also ask" and "Related searches" sections
3. Scan the top 5 ranking pages for vocabulary they consistently use
4. Look at section headings on those pages — these are the subtopics the engine expects

### Examples of semantic vocabulary by topic

**Target: "cordless drill"**
Expected vocabulary: battery voltage, chuck size, torque, clutch settings, brushless motor, DeWalt, Makita, Milwaukee, drill bits, RPM, variable speed, keyless chuck, 18V/20V, impact driver

**Target: "sourdough bread"**
Expected vocabulary: starter, levain, bulk fermentation, proofing, scoring, Dutch oven, hydration, gluten, autolyse, crumb structure, crust, yeast

**Target: "project management software"**
Expected vocabulary: task management, Gantt chart, milestones, team collaboration, deadline tracking, Asana, Jira, Trello, agile, sprint, backlog, dependencies, reporting

If a page about "cordless drills" never mentions any of these associated concepts, it looks thin to a sophisticated search engine even if it includes the exact phrase multiple times.

---

## Content Depth vs. Content Length

Content length and content depth are related but not the same. The goal is **depth**, not word count.

### Signs of deep content

- Covers all the main questions a searcher would have on this topic
- Addresses multiple angles: definitions, how-to, comparison, use cases, common mistakes
- Uses specific data, examples, or original research
- Has subtopics organized by meaningful headings (not arbitrary breaks)
- Anticipates follow-up questions and answers them

### Signs of shallow content masquerading as long content

- Repetitive paragraphs saying the same thing in different words
- Headers that promise a subtopic but the section underneath says nothing substantive
- Padding ("in this article, we will discuss…"; "now that we've learned X, let's look at Y")
- Large amounts of boilerplate that appears across many pages (policy text, disclaimers filling content space)

**The test:** Can you remove 25% of the words without losing any information? If yes, the content needs editing, not more words.

---

## Thin Content Threshold Guide

Search engines define thin content loosely, but these patterns consistently trigger quality filters:

| Pattern | Risk level |
|---|---|
| Fewer than ~30–50 unique, parsable sentences | High |
| Content that changes only proper nouns from a template (city names, product names) | High |
| Duplicate title tags across multiple pages | High |
| Near-duplicate meta descriptions across multiple pages | Medium |
| No body content unique to this page vs. other pages on the site | High |
| Auto-generated text from product feeds with no editorial addition | Medium–High |
| Pages that exist only as navigation (category pages with only links, no text) | Medium |

### Thin content fixes

| Thin content type | Fix |
|---|---|
| Location page with only address swapped | Add unique local detail: directions, staff names, photos, local reviews, location-specific hours |
| Product page using manufacturer description verbatim | Rewrite with editorial voice; add use cases, comparisons, buyer guidance |
| Category page with no introductory text | Add 100–200 words of keyword-rich intro above the product grid |
| Blog post that is just a list of links | Add editorial context around each link; expand each item into a substantive entry |
| FAQ page with one-sentence answers | Expand each answer to 50–100 words with specifics |

---

## Long-Tail Keyword Capture Strategy

Long-tail queries (low-volume individual phrases that collectively represent ~70% of all search traffic) are captured by depth, not by creating individual pages for every phrase.

### How depth captures long-tail traffic

A page about "New York pizza delivery" can also rank for:
- "Pizza delivery near Times Square"
- "Best sausage pizza in Manhattan"
- "Late night pizza delivery 10036"
- "Is there good pizza delivery in Midtown?"

— if the body content naturally addresses neighborhoods, ingredients, specific areas, and times.

### Depth tactics for long-tail capture

1. **Include geographic specifics** — neighborhoods, landmarks, ZIP codes, local references
2. **Include product/service specifics** — models, variants, sizes, materials, brands
3. **Include use-case scenarios** — who would buy this? When? Why? Under what circumstances?
4. **Include comparison context** — how does this compare to alternatives?
5. **Include FAQ-style content** — the most common questions in your topic area, answered in the body
6. **Include process detail** — step-by-step instructions naturally generate long-tail match vocabulary

### Long-tail and content uniqueness

For multi-location sites (e.g., 100 pizza locations), the challenge is creating content that is both unique per page and comprehensive enough to capture long-tail traffic:

- Each location page should include: area-specific driving directions, neighborhood information, location-specific staff or specialties, location-specific hours and parking, local reviews
- The goal is that a user reading any individual location page would receive information genuinely useful for that specific location — not information that would apply to any of the 100 locations identically

---

## Heading Tag Structure Reference

### Correct heading hierarchy

```html
<h1>Primary topic — appears once per page</h1>

  <h2>Major subtopic 1</h2>
    <h3>Sub-point within subtopic 1</h3>
    <h3>Sub-point within subtopic 1</h3>

  <h2>Major subtopic 2</h2>
    <h3>Sub-point within subtopic 2</h3>

  <h2>Major subtopic 3</h2>
```

### Common heading errors

| Error | Impact | Fix |
|---|---|---|
| No H1 on page | High — primary topical signal missing | Add an H1 that contains the primary keyword |
| Multiple H1 tags | Medium — dilutes the signal | Keep one H1; convert extras to H2 |
| H1 contains low-value content (date, category name, author) | Medium | Change H1 to article title or primary topic |
| Heading tags used for visual styling, not structure | Low–Medium | Separate visual styling into CSS; use headings semantically |
| Skipped levels (H1 → H3 with no H2) | Low | Fill in the missing levels; maintain hierarchy |
| Keyword not in H1 | Medium | Rewrite H1 to include primary keyword naturally |
| All headings use the same keyword phrase | Medium | Vary headings to cover subtopics and related terms |

---

## Boldface and Emphasis Tags

Using `<strong>` (bold) or `<em>` (italic) on keyword instances provides a small positive ranking signal. Guidelines:

- Apply `<strong>` to the primary keyword on its 1–2 most prominent appearances per page
- Do not bold every occurrence of the keyword — over-bolding provides no additional signal and hurts readability
- Use `<em>` for semantic emphasis, definitions, or foreign terms — not for keyword stuffing
- Never use `<b>` or `<i>` for structural heading content — use heading tags instead

---

## CSS and Code Quality Impact

| Factor | Ranking impact | Practical action |
|---|---|---|
| External CSS file | Low direct; positive indirect (page speed) | Always store CSS externally |
| Inline CSS on content elements | Low | Move to external stylesheet |
| JavaScript blocking content render | Medium | Move JS to external files; load deferred or async |
| Page load time (from code bloat) | Medium (affects crawl rate and user behavior) | Minimize HTML; cache aggressively |
| Tableless CSS layout | Low direct; positive indirect (crawlability) | Use CSS layouts; avoid table-based structure |
| Code-to-text ratio | Low direct; positive for large sites | Reduce HTML boilerplate; increase content ratio |
| Semantic HTML elements | Low direct; helps crawler understanding | Use `<article>`, `<section>`, `<nav>`, `<aside>` where applicable |
