# Keyword Mapping: Page-Type Framework and Cannibalisation Audit

Keyword mapping is the process of assigning every target keyword to exactly one URL on the site. Done well, it eliminates cannibalisation, clarifies the content roadmap, and ensures each page is built to satisfy one clear intent.

---

## The core rule

**One primary keyword per URL.**

A page can target dozens of semantically related secondary keywords — but it must have a single primary keyword that defines the page's purpose, title tag, and H1. When two pages compete for the same primary keyword, search engines can't determine which one to rank and often rank neither.

---

## Page-type decision framework

Use intent + funnel stage to determine which page type a keyword belongs on.

### Full decision matrix

| Intent | Funnel stage | User goal | Best page type | Secondary formats |
|---|---|---|---|---|
| Informational | Awareness | Understand a concept or problem | Long-form guide / pillar post | Explainer, glossary entry |
| Informational | Awareness | Answer a specific question | FAQ post or standalone Q&A | Blog post with clear answer |
| Informational | Consideration | Learn how to do something | Tutorial / how-to guide | Step-by-step blog post |
| Commercial investigation | Consideration | Compare options | Comparison page (X vs Y) | Roundup / best-of list |
| Commercial investigation | Consideration | Evaluate a specific option | Review page | Case study |
| Commercial investigation | Consideration | Find solutions for a use case | Use case / solution page | Landing page with editorial content |
| Transactional | Decision | Sign up, buy, or request a demo | Dedicated landing page | Homepage (for brand terms) |
| Transactional | Decision | Purchase a specific product | Product page | Category page |
| Transactional | Decision | See pricing | Pricing page | — |
| Navigational | Any | Find a specific page | Exact page they're looking for | — |
| Local | Decision | Find a business near them | Location-specific landing page | Google Business Profile |
| Feature-specific | Consideration / decision | Understand a product feature | Feature page | Product tour page |

---

## How to build the keyword map

### Step 1: List all target keywords

After completing evaluation and prioritisation (Step 4 of the main skill), you have a ranked keyword list. Export it — one row per keyword, with volume, KD, intent, and priority score.

### Step 2: Group by intent cluster

Sort keywords into clusters where the user intent is essentially the same. Keywords with identical or very similar intent belong on the same page — not separate pages.

**Example cluster:**
- "how to reduce employee turnover" (primary)
- "employee retention strategies" (secondary)
- "how to improve staff retention" (secondary)
- "reduce staff turnover tips" (secondary)

All of these belong on one page. The primary keyword goes in the title tag and H1. Secondary keywords are covered naturally in the body copy, subheadings, and meta description.

**Signal that keywords should NOT be clustered:**
- The SERP results are meaningfully different for each term (different page types rank)
- The user goal is different even if the topic overlaps
- The best page format is different (e.g., one needs a tool, the other needs a guide)

### Step 3: Match each cluster to a URL

For each cluster, assign it to either:
- **An existing page** — if a page already exists that covers this intent (or could be updated to)
- **A new page** — if no existing page satisfies this intent

Assign a target slug for new pages at this stage. Keyword-rich, short, and clear:
- `/employee-retention-strategies/` ✓
- `/blog/2023/how-to-keep-your-employees-from-leaving-the-company/` ✗

### Step 4: Set page status and action

For each keyword-to-page assignment, mark:

| Status | Meaning | Action |
|---|---|---|
| **New** | No page exists for this intent | Create |
| **Existing – strong** | Page exists and ranks reasonably well | Strengthen (add secondary keywords, improve depth) |
| **Existing – weak** | Page exists but thin, outdated, or not ranking | Update and expand |
| **Existing – wrong type** | Page exists but wrong format for this intent | Rebuild or supplement |
| **Cannibalisation risk** | Two pages competing for same keyword | Consolidate |

---

## Cannibalisation audit

Keyword cannibalisation occurs when two or more pages on the same site compete for the same primary keyword. Search engines split authority between them — both pages rank lower than either would alone.

### How to identify cannibalisation

**Method 1: Site search**
Search `site:yourdomain.com [keyword]` in Google. If more than one page appears prominently in the results, you likely have a cannibalisation issue.

**Method 2: Google Search Console**
Filter Performance by query → find keywords where multiple URLs appear in the "Pages" tab for the same query. If traffic is split across two pages for a keyword, they're cannibalising.

**Method 3: Keyword tool audit**
In Ahrefs or Semrush, export all ranking keywords and check for instances where the same keyword is the top-ranking keyword for two different URLs on your domain.

**Method 4: Manual mapping review**
When building the keyword map, flag any case where two rows point to different URLs with the same or near-identical primary keyword.

### How to resolve cannibalisation

**Option A: Consolidate (preferred)**
Merge the content of both pages into one stronger page. 301-redirect the weaker URL to the page you're keeping. Update all internal links to point to the surviving page.

Best when: Both pages cover the same topic, the combined content will be stronger, one URL is clearly more authoritative.

**Option B: Differentiate**
Update each page to target a meaningfully different intent or audience, so they no longer compete.

Best when: The keyword variants actually have different intent and you want to capture both.

**Option C: Canonicalise**
Add a canonical tag on the weaker page pointing to the primary page, without deleting the weaker page.

Best when: You need both URLs to exist (for UX or technical reasons) but want to consolidate ranking signals.

**Option D: Noindex the weaker page**
Best when: The weaker page has no standalone value and you'd rather it not be crawled at all.

---

## Keyword map template

Use this format for the keyword-to-page map section of your output:

```
| Primary keyword | Monthly vol | Secondary keywords | Target URL | Page type | Status | Action |
|---|---|---|---|---|---|---|
| [keyword] | [vol] | [kw2, kw3, kw4] | /[slug] | [type] | New / Existing | Create / Update / Consolidate |
```

**Example:**

| Primary keyword | Monthly vol | Secondary keywords | Target URL | Page type | Status | Action |
|---|---|---|---|---|---|---|
| employee retention strategies | 2,400 | how to reduce turnover, staff retention tips, keep employees | /employee-retention-strategies/ | Long-form guide | New | Create |
| best HR software small business | 1,900 | HR tools for small teams, HR software comparison | /best-hr-software-small-business/ | Comparison page | New | Create |
| HR software pricing | 880 | how much does HR software cost, HR software cost | /pricing/ | Pricing page | Existing – weak | Update (add keyword to title tag and H1) |
| BambooHR vs Gusto | 720 | BambooHR vs Gusto comparison, BambooHR alternative | /bamboohr-vs-gusto/ | Comparison page | New | Create |
| how to onboard new employees | 590 | employee onboarding checklist, new hire onboarding process | /employee-onboarding-guide/ | Tutorial / guide | Existing – strong | Strengthen (add secondary keywords) |

---

## Mapping pitfalls to avoid

**Creating a new page for every keyword variant.**
"CRM for startups" and "CRM software for small business" likely have the same intent. One page handles both. Don't create two.

**Mapping high-volume keywords to thin pages.**
Assigning a 2,000-search/month keyword to a 300-word blog post sets it up to fail. The page depth must match the competitive intensity of the keyword.

**Assigning transactional keywords to informational pages.**
A blog post will not rank for "buy project management software." These keywords need dedicated landing pages built with conversion intent.

**Ignoring existing cannibalisation before adding new keywords.**
If two pages are already competing for a keyword, adding a third page won't fix it. Audit and consolidate first.

**Using folder-deep slugs for important pages.**
`/blog/category/2022/november/post-title/` buries pages. Important target pages should live at `/topic-keyword/` — shallow, clean, keyword-present.

**Mapping everything to the homepage.**
The homepage can target one or two very broad brand terms. It cannot absorb 30 different keyword intents. Each distinct intent needs its own page.
