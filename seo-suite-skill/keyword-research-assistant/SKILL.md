---
name: keyword-research-assistant
description: Perform deep keyword research for any topic, site, or campaign. Use this skill whenever the user wants to find keywords to target, understand what their audience is searching for, build a keyword list from scratch, prioritize keywords by difficulty or intent, expand an existing keyword strategy, identify keyword gaps vs competitors, or map keywords to pages. Also trigger when the user says things like "what keywords should I target", "help me find keywords for X", "what is my audience searching for", "I need to do keyword research", "find me long-tail keywords for Y", or "what keywords is my competitor ranking for."
---

# Keyword Research Assistant

Perform rigorous, intent-first keyword research that produces a prioritized, actionable list — not just a volume-sorted spreadsheet.

The core principle: keyword research is user research. The goal is to understand *what your audience is looking for, in their own words, at every stage of their journey* — then find the most efficient path to earning those rankings based on your site's current authority and competitive position.

Volume is a data point, not a decision. A keyword with 150 searches/month that perfectly matches a buyer's intent is worth more than one with 15,000 searches/month that your site has no realistic chance of ranking for.

---

## Step 1: Gather inputs

Before building a keyword list, understand the context. Extract from what the user has shared; ask only for what's genuinely missing and essential.

**Required:**
- Topic, niche, or business description
- Target audience (who are the users — their role, knowledge level, goals)
- Primary business goal (traffic, leads, signups, revenue, brand awareness)

**Important:**
- Site URL (if it exists) — to assess current authority and ranking opportunities
- Funnel stage focus — are we targeting top-of-funnel awareness, mid-funnel consideration, or bottom-of-funnel conversion?
- Any seed keywords already known
- Key competitors (if known)

**Nice to have:**
- Google Search Console data (which queries already drive impressions/clicks)
- Existing content on the site (to identify gaps and avoid cannibalization)
- Geographic targeting — local, national, or global?
- Industry or vertical (affects seasonality, jargon, user terminology)

If the user gives you a topic and nothing else, make reasonable inferences, state them clearly, and proceed. Don't interrogate before delivering value.

---

## Step 2: Build the seed keyword list

Start before opening any tool. Seed keywords are the raw starting material — the user's own vocabulary for their problem.

### Seed generation methods

**1. Jobs-to-be-done approach**
List every task, problem, or goal your target user has that relates to this topic. Write them as the user would phrase them — not in product or industry jargon.

Example: For an HR software company:
- "how to automate employee onboarding"
- "track employee time off"
- "performance review templates"
- "how to manage remote teams"

**2. Funnel-stage mapping**
Generate seeds at each funnel stage:

| Stage | User mindset | Query type | Example |
|---|---|---|---|
| Awareness | Recognising a problem | "Why does X happen", "What is Y" | "why does employee turnover increase" |
| Consideration | Researching solutions | "How to X", "Best tools for Y" | "how to reduce employee turnover" |
| Decision | Evaluating options | "X vs Y", "Best X for Z" | "best HR software for small business" |
| Retention | Getting more value | Tutorials, feature-specific | "how to set up PTO tracking in [tool]" |

**3. Competitor content audit**
What content are your competitors ranking for? Use a backlink and keyword tool (Ahrefs, Semrush, Moz) to pull their top organic pages. These represent validated demand in your space.

**4. User language sources**
Harvest actual user language from:
- Reddit threads on the topic
- Quora questions
- Review sites (G2, Trustpilot, Amazon) — the language in reviews is gold
- Customer support tickets and sales call transcripts
- Community forums and Slack/Discord groups

> See [references/seed-generation.md](references/seed-generation.md) for expanded seed-building tactics by industry and use case.

---

## Step 3: Expand keywords systematically

Once you have seeds, expand them using a structured framework.

### Expansion methods

**1. Question modifiers**
Prepend common question starters to your seeds:
- how to / how do I / how does
- what is / what are / what's the best
- why does / why is / why can't
- when to / when should
- which [option] is better

**2. Qualifier modifiers**
Append qualifiers that reflect user specificity:
- for [audience segment]: "for small business", "for beginners", "for enterprise"
- by [method]: "without X", "using Y", "with Z tool"
- [location]: "in [city]", "[country] [keyword]"
- [comparison]: "vs", "alternative to", "compared to"
- [urgency/context]: "fast", "free", "template", "checklist", "examples"

**3. Related topic clusters**
For each seed, list all semantically adjacent topics. These often reveal keyword gaps your competitors have missed.

**4. Long-tail variants**
For every broad term, generate 5–10 specific variants. These are typically 3–6 word phrases with clear, narrow intent. They're faster to rank for, easier to satisfy with a single page, and convert at higher rates.

> See [references/expansion-framework.md](references/expansion-framework.md) for modifier libraries by intent type and industry-specific expansion patterns.

---

## Step 4: Evaluate and prioritise keywords

A keyword is only worth targeting if you can realistically rank for it in a timeframe that matters. Evaluate each keyword on these dimensions:

### The four filters

**1. Search volume**
Monthly search volume is a proxy for demand — not a target in itself. Guidelines:
- 0–50/month: Niche, long-tail. Often underreported. Worth targeting if intent is perfect.
- 50–500/month: Sweet spot for most mid-tier sites. Good ROI, achievable.
- 500–5,000/month: High value, moderate competition. Requires solid authority.
- 5,000+/month: Highly competitive head terms. Requires strong domain authority. Don't prioritise until mid-funnel content is established.

**2. Keyword difficulty (KD)**
Keyword difficulty scores (from tools like Ahrefs, Semrush, or Moz) estimate how hard it is to rank on page 1. Interpret them relative to your site's domain authority:

| KD score | Meaning | Who can target it |
|---|---|---|
| 0–20 | Low competition | Any site, even new ones |
| 21–40 | Moderate competition | Sites with some established content |
| 41–60 | Competitive | Sites with decent domain authority (DA 30–50) |
| 61–80 | Highly competitive | Established sites with strong link profiles |
| 81–100 | Extremely competitive | Major brands and high-authority domains only |

**3. Search intent match**
Does this keyword match the intent of the page you're planning to build? This is the most important filter. A page can't rank for a keyword whose intent it doesn't satisfy — even with perfect on-page optimisation.

Classify every keyword by intent type:
- **Informational** — user wants to learn or understand
- **Navigational** — user is looking for a specific site or page
- **Commercial investigation** — user is researching before deciding
- **Transactional** — user is ready to take action

> See [references/intent-classification.md](references/intent-classification.md) for detailed intent signals and SERP feature patterns by type.

**4. Business relevance**
Will traffic from this keyword convert into your business goal? Rate each keyword 1–3:
- **3** — Direct connection to conversion (buys, signups, leads)
- **2** — Indirect — builds brand awareness with target audience
- **1** — Tangential — attracts traffic but weak connection to the product

Prioritise keywords with high business relevance even if volume is lower.

### Priority scoring matrix

Use this formula to stack-rank keywords:

```
Priority score = (Business relevance × 3) + (Achievability score) + (Intent match score)

Achievability: KD ≤ 20 → 5pts | KD 21–40 → 4pts | KD 41–60 → 2pts | KD 61+ → 0pts
Intent match: Exact match → 3pts | Strong match → 2pts | Partial → 1pt
```

Sort your keyword list by priority score descending. The top of that list is your roadmap.

> See [references/prioritisation-scoring.md](references/prioritisation-scoring.md) for the full scoring model with worked examples.

---

## Step 5: Map keywords to pages

Every keyword must be assigned to exactly one page. This is the rule that prevents keyword cannibalization.

### Mapping rules

- **One primary keyword per URL.** Two pages competing for the same term split authority and confuse search engines. Both lose.
- **Cluster related keywords together.** Secondary keywords and semantic variants should all live on the same page as the primary keyword.
- **Match keyword intent to page type.** Informational keywords go on guides and blog posts. Transactional keywords go on landing pages, product pages, or pricing pages.
- **New keyword = new page only if it has meaningfully different intent.** If the user intent is the same as an existing page, add the keyword to that page's target list — don't create a new one.

### Page type assignments

| Keyword intent + funnel stage | Assign to |
|---|---|
| Informational / awareness | Blog post, guide, explainer |
| Commercial / consideration | Comparison page, use case, review |
| Transactional / decision | Landing page, product page, pricing |
| Navigational / brand | Homepage, about page, product page |
| Local / intent | Location-specific landing page |
| Question-based | FAQ section, standalone Q&A post |
| Feature / tool | Dedicated feature page or tool landing page |

### Identifying gaps

After mapping keywords to existing pages, look for:
- **Uncovered queries** — High-priority keywords with no matching page → create new content
- **Weak coverage** — Medium-priority keywords on thin pages → update and strengthen
- **Cannibalisation risks** — Multiple pages targeting the same keyword → consolidate

> See [references/keyword-mapping.md](references/keyword-mapping.md) for the full page-type decision framework and cannibalisation audit process.

---

## Step 6: Competitive keyword gap analysis

Find keywords your competitors rank for that you don't. These represent demand in your market that you're invisible for.

### Gap analysis process

1. **Identify 3–5 true SEO competitors** — sites ranking for the same keywords your users search, not necessarily your direct business competitors
2. **Pull their top ranking pages** using Ahrefs, Semrush, or similar — filter to pages with 500+ monthly organic visits
3. **Cross-reference against your site** — which of their top keywords do you not rank in the top 20 for?
4. **Filter by your authority and difficulty** — identify the gaps you can realistically close in 6–12 months
5. **Add qualified gaps to your keyword map** as new content opportunities

### What to look for

- **Content format gaps** — they have a comprehensive guide on a topic; you have nothing
- **Intent gaps** — they're capturing decision-stage traffic with comparison pages; you only have awareness content
- **Modifier gaps** — they rank for "[keyword] for [your specific audience]" and you don't
- **Long-tail gaps** — they've built topical depth with 50+ cluster posts; you have one thin blog post

---

## Step 7: Deliver the output

Produce a structured keyword research output the user can immediately act on.

### Output format

```
# Keyword Research: [Topic/Site/Campaign]

## Research summary
- Total keywords evaluated: [X]
- Keywords recommended for targeting: [Y]
- Estimated total monthly search volume (recommended set): [Z]
- Key opportunity areas identified: [2–3 sentences]

---

## Priority 1: Quick wins (low KD, high intent match)
Target these first — fastest path to organic traffic.

| Keyword | Monthly volume | KD | Intent | Page type | Priority score |
|---|---|---|---|---|---|
| [keyword] | [vol] | [KD] | [type] | [page] | [score] |
...

---

## Priority 2: Core targets (medium KD, high business value)
These require more authority but drive the most business-relevant traffic.

| Keyword | Monthly volume | KD | Intent | Page type | Priority score |
|---|---|---|---|---|---|
...

---

## Priority 3: Long-term plays (high volume, high competition)
Build toward these once Priorities 1 and 2 are established.

| Keyword | Monthly volume | KD | Intent | Page type | Notes |
|---|---|---|---|---|---|
...

---

## Keyword-to-page map
| Keyword (primary) | Secondary keywords | Target URL | Page status | Action |
|---|---|---|---|---|
| [keyword] | [kw2, kw3] | /[slug] | Existing / New | Create / Update / Strengthen |
...

---

## Competitive gap opportunities
Keywords your competitors rank for that you don't — highest-value gaps only.

| Keyword | Competitor ranking | Your position | Opportunity |
|---|---|---|---|
...

---

## What NOT to target (and why)
Keywords excluded from recommendations with explanation:
- [keyword] — too competitive for current domain authority (KD 78)
- [keyword] — mismatched intent with available page types
- [keyword] — already covered by existing page [/url] — update that page instead
- [keyword] — zero business relevance despite high volume

---

## Recommended next steps
1. [Most impactful action — e.g., create X pages for Priority 1 quick wins]
2. [Second action — e.g., update existing page /url to target keyword cluster Y]
3. [Third action — e.g., run competitive gap analysis deeper on Topic Z]
```

---

## Quality checks before delivering

Before presenting keyword research, verify:

- [ ] Every keyword has a clear intent classification — no ambiguous classifications left unresolved
- [ ] No two keywords in Priority 1 or 2 have identical intent targeting the same page (cannibalisation check)
- [ ] Volume figures are provided for context, not presented as the primary ranking factor
- [ ] Keyword difficulty is interpreted relative to the site's actual authority, not as an absolute
- [ ] Every recommended keyword has a clear page assignment
- [ ] Quick wins are genuinely achievable — KD scores match the site's realistic authority level
- [ ] The output is actionable, not just a sorted list — the user knows exactly what to do next

---

## Common mistakes to avoid and call out

These appear frequently — flag them when they appear in the user's thinking or context:

**Targeting head terms before establishing topical authority.** A new site cannot rank for "project management software." Start with "how to manage remote team projects" — earn authority, then work up.

**Treating volume as importance.** A 100-search/month keyword from a high-intent buyer is worth more than a 10,000-search/month keyword from a casual reader who will never convert.

**Ignoring zero-volume keywords.** Keyword tools undercount long-tail queries. Many valuable terms show 0 monthly searches in tools but generate real traffic once you rank. Don't eliminate a keyword just because a tool can't measure it.

**Building pages for every keyword variant.** "Best CRM for startups" and "CRM software for small business" likely have the same user intent and should be covered on one page, not two.

**Skipping the intent check.** Optimising a transactional landing page for an informational keyword, or vice versa, will never rank regardless of other quality. Intent match is not optional.

**Confusing SEO competitors with business competitors.** The sites your sales team monitors are not necessarily your SEO competitors. Your SEO competitor is whoever is ranking for the keywords your users search — which may include media sites, tools, and directories, not just direct product rivals.
