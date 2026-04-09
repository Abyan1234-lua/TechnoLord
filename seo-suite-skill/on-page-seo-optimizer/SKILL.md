---
name: on-page-seo-optimizer
description: Optimize individual pages and site-wide content elements for maximum search engine relevance and ranking potential. Use this skill whenever the user wants to optimize title tags, meta descriptions, heading structure, body content, URLs, image attributes, or internal linking on any page or set of pages. Also trigger when users say "how do I optimize this page", "what should my title tag say", "how do I write meta descriptions", "my page isn't ranking despite links", "what keywords should I put on the page", or "how do I fix thin content."
source: The Art of SEO — Eric Enge, Stephan Spencer, Rand Fishkin & Jessie C. Stricchiola (O'Reilly Media, 2009)
---

# On-Page SEO Optimizer

Maximize the relevance signals on every page so that search engines have no ambiguity about what it covers, who it's for, and why it deserves to rank.

The core principle: **On-page SEO is about reducing uncertainty. Every signal — title, heading, body text, URL, image alt — should reinforce the same primary topic. Inconsistency between signals is the most common reason well-linked pages underperform.**

Two truths to hold together:
1. **Keyword placement matters.** Search engines still rely on the words on your page to understand its topic. A page without the target phrase in its title and headings will almost never rank for it.
2. **Keyword stuffing is penalized.** The goal is natural, well-structured content that uses the target phrase and related terms organically — not mechanical repetition.

---

## How to use this skill

Jump to the most relevant phase based on the user's situation.

- **"Optimize this specific page"** → Run all phases top to bottom for that URL
- **"Fix our title tags across the site"** → Phase 1 only
- **"Write meta descriptions for our landing pages"** → Phase 2 only
- **"Our headings are a mess"** → Phase 3 only
- **"How much should we write? What goes in the content?"** → Phase 4
- **"Our URLs are terrible"** → Phase 6
- **"We have pages competing with each other"** → Phase 7 (Cannibalization)
- **"We have a large site / CMS and can't optimize manually"** → Phase 8 (Scale)
- **"Audit this page and give me a report"** → Use the Audit Output Format at the bottom

---

## Phase 1: Title Tags — The Most Important On-Page Element

The title tag is the single most important on-page ranking factor. In surveys of SEO professionals ranking the factors in Google's algorithm, the title tag consistently comes out at the top. It is the only piece of "meta" information in the `<head>` that directly influences relevancy and ranking.

It also appears as the clickable headline in search results — it must work for both the algorithm and the human reading the SERP.

### The 8 rules of title tag construction

**1. Keywords at the front**
Place the primary keyword as close to the start of the title as possible. Search engines give more weight to words that appear early. Brand names, unless they are the primary search target, go at the end.

Exception: Major brands with strong recognition may benefit from leading with the brand name to increase click-through from brand-loyal searchers. This is a deliberate tradeoff — make it explicitly, not accidentally.

**2. Keep it under 65 characters (including spaces)**
Content after ~65 characters is truncated in SERPs and may receive less ranking weight. Target 50–65 characters as the sweet spot. Google sometimes displays up to 70, but 65 is the safe ceiling.

**3. Include the primary keyword phrase**
Always include the keyword your research identified as the most valuable for this specific page. Do not rely on the engine to infer relevance from body text alone.

**4. Include longer phrase variants where they fit naturally**
If the page targets "downhill skiing equipment" and "skiing accessories," and both phrases are genuinely represented in the content, both can appear in the title — e.g., `"Downhill Skiing Equipment & Accessories | SkiDudes"`. More specific, longer phrases often have higher conversion intent and lower competition.

**5. Use a divider between keyword phrase and brand**
Standard dividers: `|` (pipe), `>`, `-`, `:`. These do not provide SEO value but improve readability and help users scan the SERP. Consistent use of one divider across a site improves brand recognition in results.

**6. Write for click-through and conversion — not just ranking**
The title tag functions like a paid search ad headline. It must earn the click once it ranks. A title that ranks #3 but gets a 15% CTR beats a title that ranks #1 with a 5% CTR in absolute traffic terms.

Consider: is the searcher in research mode or purchase mode? Adjust language accordingly.
- Research intent: descriptive and informative — `"What Is Sourdough Starter? A Complete Guide"`
- Purchase intent: action-oriented — `"Buy Sourdough Starter Kits — Free Shipping"`

**7. Target searcher intent accurately**
The title should match what the searcher expects to find. A title promising "free" content that leads to a paywall destroys trust. Accuracy in titles improves conversion rates and reduces bounce rates — both of which feed back into rankings.

**8. Be consistent within sections**
Establish a title formula for each section of the site (product pages, blog posts, category pages) and stick to it. Consistency trains users to recognize your brand in SERPs and sets expectations that your pages reliably fulfill.

### Title tag formulas by page type

| Page type | Formula | Example |
|---|---|---|
| Homepage | `[Brand] — [Primary Value Proposition]` | `"Acme Tools — Professional Power Tools & Equipment"` |
| Category page | `[Category Keyword] — [Brand]` | `"Cordless Drills — Acme Tools"` |
| Product page | `[Product Name] [Key Attribute] — [Brand]` | `"DeWalt 20V MAX Cordless Drill — Acme Tools"` |
| Blog post | `[Target Keyword]: [Compelling Description]` | `"How to Choose a Cordless Drill: 7 Key Factors"` |
| Location page | `[Business] [Service] in [City, State]` | `"Acme Tools — Power Tools in Austin, TX"` |
| Landing page | `[Action] [Keyword] — [Value Differentiator]` | `"Buy Cordless Drills — Best Prices, Free Shipping"` |

> See [references/title-and-meta-templates.md](references/title-and-meta-templates.md) for formulas, character counting guide, and common errors.

---

## Phase 2: Meta Description Tags

Meta descriptions do not directly influence rankings. They influence **click-through rate** from the SERP — which does affect traffic volume and may indirectly feed back into rankings.

Three roles of the meta description:
1. Describe the page content accurately and succinctly
2. Function as a short advertisement that competes for the click
3. Show the target keyword (search engines bold matching terms in the SERP snippet, increasing visual salience)

### 7 rules for meta descriptions

**1. Tell the truth**
Accurately represent the page. Misleading descriptions that earn clicks but fail to deliver what they promised increase bounce rates and damage brand trust. Improve the content, not the description.

**2. Keep it under 160 characters**
Google displays ~155–160 characters; Yahoo! up to 165; Bing up to 200+. Target 150–155 characters to stay within all engines' limits with a small buffer.

**3. Write it like an ad**
The best meta description reads like high-quality ad copy: specific, compelling, and action-oriented. It must earn the click in competition with 9 other results.

**4. Include the primary keyword**
When the search query matches words in the meta description, search engines bold those words in the snippet. This visual highlighting increases click-through. Always include the page's target keyword.

**5. Test and refine**
Use PPC ad testing to iterate on meta description copy. Run the same text as an ad for 1–2 weeks, measure CTR, and incorporate winning language into the organic meta description.

**6. Match intent to searcher psychology**
Organic searchers and paid searchers often have different mindsets. A high-converting PPC ad may emphasize price and urgency; an organic searcher may be in research mode and respond better to depth and expertise signals. Test both approaches.

**7. Don't write meta descriptions for every page**
For pages targeting one to three high-volume keywords, a custom meta description is worth the effort. For large-scale content (hundreds of blog posts, thousands of product pages), let the engine extract the relevant surrounding text automatically — it will always display the words that match the user's query, which a fixed description may not. Forced descriptions can hurt long-tail performance.

---

## Phase 3: Heading Tags (H1–H3)

Heading tags signal document hierarchy to search engines. The `<h1>` is the page-level headline — the primary topical signal after the title tag. `<h2>` and `<h3>` tags are subtopic dividers.

### H1 rules

- Every page must have exactly one `<h1>` tag
- The `<h1>` should be the article title, product name, category name, or primary topic — the first thing a user reads when they land on the page
- It must contain the page's primary keyword
- It can be the same as the title tag, or a slightly longer/shorter variant — both are acceptable
- Low-value content (publication date, author name, category label) should **not** be the `<h1>`
- Too many `<h1>` tags on one page dilutes the signal — one per page is the rule

### H2 and H3 rules

- Use `<h2>` for main subtopics; use `<h3>` for sub-subtopics within an `<h2>` section
- Include relevant secondary keywords and related phrases in `<h2>` tags — this builds topical depth
- Heading hierarchy must be logical: `<h1>` → `<h2>` → `<h3>` — do not skip levels
- Visual styling does **not** determine SEO weight — a tiny-font `<h1>` is still an `<h1>`; style headings however the design requires

### Heading structure example

```html
<h1>Cordless Drill Buying Guide</h1>           <!-- Primary keyword + page topic -->

  <h2>Key Specifications to Consider</h2>      <!-- Main subtopic -->
    <h3>Voltage and Battery Life</h3>          <!-- Sub-subtopic -->
    <h3>Chuck Size and Clutch Settings</h3>

  <h2>Best Cordless Drills by Use Case</h2>
    <h3>Best for Home DIY</h3>
    <h3>Best for Professional Use</h3>

  <h2>How to Compare Prices and Value</h2>
```

---

## Phase 4: Body Content Optimization

### The right mental model for keyword usage in body text

Keyword density as a metric is obsolete. Search engines no longer count keyword instances to determine relevance — they evaluate topical context, semantic relationships, and user satisfaction signals. What matters is:

1. The target phrase appears on the page (at least once, and naturally a few more times in longer content)
2. Related terms and semantic variants appear throughout the content
3. The content actually answers what the searcher is looking for

A page with 2 natural uses of "cordless drill" and rich supporting content about batteries, torque, brands, and use cases will outrank a page with 15 mechanical uses of "cordless drill" and no supporting depth.

### Keyword placement priority

Place the primary keyword in these locations, in priority order:

1. **Title tag** — highest weight (Phase 1)
2. **H1 heading** — second highest
3. **First 100 words of body text** — early placement signals topical focus
4. **At least one H2 heading** — reinforces topic across subtopics
5. **Throughout the body** — naturally, 2–5 times per 500 words depending on length
6. **Image alt attributes** — where images are directly related to the keyword
7. **URL** — lower weight but still a signal (Phase 6)
8. **Meta description** — for CTR, not direct ranking

### Using related terms and semantic context

Search engines build a vocabulary of concepts that co-occur with each topic. A page about "cordless drills" that also naturally includes terms like "battery voltage," "drill bits," "torque settings," "chuck," "DeWalt," "Makita," and "brushless motor" will rank more strongly than one that only contains the phrase "cordless drill."

Practical technique: search for your target keyword in Google, look at the top-ranking pages, and note the vocabulary and subtopics they consistently cover. Your page should address the same conceptual territory.

### Boldface text

Using `<strong>` or `<b>` tags on keyword instances has a small positive effect on relevance signals. Use sparingly — on the 1–2 most important keyword instances per page — not on every occurrence. Over-bolding creates a poor reading experience and the signal diminishes with overuse.

### Content length

Content length is not a direct ranking signal — but it correlates with comprehensiveness, which is. Longer content tends to:
- Cover more related terms naturally
- Answer more questions a searcher might have
- Earn more links (more linkable material)
- Rank for more long-tail variants

However, splitting long content into multiple short segments typically backfires:
- Abandonment rates increase
- Link attraction decreases (multiple thin pages vs. one comprehensive page)
- Internal link equity is diluted

**Rule:** Make content as long as it needs to be to be the most useful answer to the searcher's question — not longer, not shorter.

### Content uniqueness — avoiding "thin content"

Search engines actively filter out thin content. The threshold signals include:
- Fewer than ~30–50 genuinely unique, parsable sentences
- Content that is merely a template with key nouns swapped (e.g., a city-name replaced across 100 location pages)
- Title and meta tags duplicated across many pages
- No unique value not available on other pages or other sites

**Thin content is not just a penalty risk — it is the reason many pages with good links still fail to rank.**

### Long-tail keyword targeting in body content

The long tail (search terms with low individual volume that collectively represent ~70% of all searches) is captured primarily through body content depth, not through individual page creation for every phrase.

A page targeting "New York pizza delivery" can also rank for "pizza delivery on the corner of 57th & 7th" and "Manhattan's best sausage pizza" if the body content addresses these variations naturally — through descriptions of neighborhoods, ingredients, specific locations, and related context.

The more specific the supporting detail in body content, the more long-tail queries a page captures without any additional optimization effort.

---

## Phase 5: Image Filenames and Alt Attributes

Search engines cannot read image content directly. Every image optimization signal is a text signal surrounding the image.

### Filename rules

- Use the primary keyword or a descriptive phrase as the filename **before uploading**
- Separate words with hyphens: `cordless-drill-review.jpg` not `cordless_drill_review.jpg` or `img4137.jpg`
- Keep filenames descriptive of what the image actually shows
- Include keywords in the directory path where natural: `/images/cordless-drills/dewalt-20v.jpg`

### Alt attribute rules

- Every meaningful image must have an `alt` attribute
- **Always use double quotes** when alt text contains spaces: `<img alt="DeWalt 20V cordless drill" src="...">`
  — Without quotes, search engines drop all words after the first. This is one of the most widespread technical errors on the web.
- Write alt text as a description for someone who cannot see the image
- Include the page's keyword naturally where the image is directly related — do not force keywords onto decorative images
- Decorative images (dividers, icons, background images) should use `alt=""`

### Context signals

- Place a descriptive caption directly below key images — this text is strongly associated with the image by both users and search engines
- The text immediately before and after an image carries extra weight as a context signal
- Images placed inside sidebar columns, headers, or footer navigation are treated as site furniture and receive lower relevance weight — keep content images in the main body

### Image links

When an image is used as a link (not just as content), the alt attribute functions as the anchor text for that link. Use keyword-relevant alt text on all image links. However, text links with explicit anchor text are substantially more powerful than image links — use text links for important internal navigation wherever possible.

---

## Phase 6: URL Optimization

URLs are a low-to-medium ranking signal but have compounding benefits: they communicate topic to users, improve click-through in SERPs, appear as anchor text when copy-pasted as links, and make internal navigation clearer for both humans and crawlers.

### URL best practices

| Rule | Good example | Bad example |
|---|---|---|
| Describe the content | `/cordless-drill-buying-guide/` | `/p?id=4728` |
| Use hyphens as separators | `/cordless-drill-review/` | `/cordless_drill_review/` or `/cordlessdrillreview/` |
| Keep it short | `/blog/sourdough-starter/` | `/blog/2024/03/19/how-to-make-sourdough-starter-at-home/` |
| Use lowercase only | `/cordless-drills/` | `/Cordless-Drills/` |
| No unnecessary folders | `/products/drills/` | `/products/category/subcategory/items/drills/` |
| Keywords where they fit naturally | `/running-shoes/trail/` | `/running-shoes/12/` |
| No tracking parameters in canonical | `/product/` | `/product/?utm_source=email` |
| No session IDs | `/product/drill/` | `/product/drill/?sess=abc123` |

### Domain name guidelines

For new domains or rebrands, apply these principles:
- Include a keyword in the domain if it doesn't compromise brand quality (e.g., `bankrate.com` beats `mortgagecalculatorsandtips.com` even though the latter has more keywords)
- Avoid hyphens and numbers in domain names — they are harder to say verbally, harder to remember, and historically associated with spammy domains
- Choose `.com` over other TLDs for general commercial sites — most users default to `.com` type-in behavior
- Never register a domain that is a plural, hyphenated, or misspelled version of a major brand
- Short, memorable, and easy-to-type domains outperform keyword-stuffed domains on all metrics: links, mentions, word-of-mouth, CTR

### URL keyword placement caveats

- Keywords in URLs provide a ranking benefit, but a URL with 8 hyphens and 12 keywords reads as spam to users and may be algorithmically flagged: `buy-cheap-cordless-drills-online-free-shipping-best-price.html` is a spam signal, not an SEO asset
- The best URL is the shortest one that accurately describes the page content with 1–2 keywords

---

## Phase 7: Keyword Cannibalization — When Pages Compete With Each Other

Keyword cannibalization is one of the most common and damaging on-page SEO problems on established sites. It occurs when multiple pages on the same site target the same or closely overlapping keyword phrases, forcing search engines to choose which one is most relevant — and often getting it wrong.

### Symptoms

- You have multiple pages ranking on page 2–3 for a term where you expect one strong page to rank on page 1
- Rankings fluctuate between different pages for the same keyword (engines keep changing their selection)
- Internal link anchor text for a keyword is spread across multiple destination pages
- Two pages have similar title tags

### How cannibalization dilutes ranking power

When two pages compete for the same keyword:
- External links pointing to either page split the equity between them
- Internal links using the keyword phrase are distributed, not concentrated
- The engine has to make an arbitrary choice between two pages it cannot clearly differentiate
- Neither page achieves the full authority it would have if it were the single, undisputed resource

### How to fix it

1. **Map your keywords to pages** — build a spreadsheet listing every target keyword and the single page that should rank for it
2. **Identify conflicts** — any keyword that maps to two or more pages is a cannibalization problem
3. **Choose the canonical page** — usually the stronger page by authority, content depth, and inbound links
4. **Consolidate** — merge the content of the weaker page into the canonical page, then 301-redirect the weaker URL to the canonical
5. **Update internal links** — ensure all internal links using the target keyword phrase point to the canonical page

### Managing parent/child keyword relationships

When one page targets a broad term and another targets a specific long-tail variant that includes the broad term:
- The specific page should link back to the broader page using the broad term as anchor text
- This signals to search engines that the broader page is the authority on the general term, while the specific page owns the variant

Example: A site with a page targeting "mortgages" and another targeting "low-interest mortgages" — the "low-interest mortgages" page should contain a link with anchor text "mortgages" pointing back to the broader page. This can appear in the breadcrumb or within the body copy.

The New York Times executes this well: keywords in body copy link to the related primary resource page on the site, creating a systematic internal linking structure that concentrates authority on canonical pages.

---

## Phase 8: On-Page Optimization at Scale (CMS and Large Sites)

Individual page-by-page optimization is impractical beyond a few hundred pages. Large sites require systematic, template-based approaches.

### Title tag generation at scale

For sites with thousands of pages, build a title tag formula per content type:

```
Product pages:    {Product Name} {Key Attribute} — {Brand}
Category pages:   {Category Name} — {Brand}
Blog posts:       {Post Title} | {Brand}
Location pages:   {Brand} {Service} in {City}, {State}
```

These formulas must:
- Be unique across all pages (the product name/category/title prevents duplication)
- Contain the primary keyword for that page's content type
- Stay within the 65-character limit

**Critical:** Educate content creators on title tag construction. Writers who do not understand SEO will produce titles like "Welcome to Our Page About X" — which wastes the most important on-page real estate.

### Meta description at scale

For large blogs, product catalogs, or news archives: omit fixed meta descriptions and let the engine extract the relevant surrounding text. Forced meta descriptions that don't contain the user's search term will rarely be displayed — and writing unique descriptions for 10,000 pages is not a practical investment.

Write custom meta descriptions only for:
- High-traffic landing pages
- Pages targeting competitive, high-value terms
- Pages where the automatically extracted text is consistently poor

### H1 at scale

The CMS must generate a unique `<h1>` per page. Common errors:
- Using the category name as the H1 on every page in a section
- No H1 at all (dates, author names, or navigation labels displayed prominently but not marked as headings)
- Multiple H1 tags per page (CMS templates pulling in section headers as H1s)

Audit H1 tags across the site with a crawler — this is one of the most consistently broken elements on large sites.

### Content uniqueness at scale

For sites that generate location pages, product variant pages, or other templated content:
- Changing only the city name and address is not sufficient for unique content — search engines recognize this pattern
- Add genuinely location-specific detail: driving directions, local staff, location-specific reviews, regional product availability, local event content
- For product variants, write unique descriptions that focus on the specific variant's attributes rather than copying the parent product description

### SEO copywriting training for content teams

When content is produced by writers who are not SEO specialists, train them on five principles:

1. Search engines match user queries to the keywords on your pages — if the phrase isn't there, the page won't rank for it
2. Some phrases are searched far more than others — use keyword research to pick the right terms
3. The title tag is the most important element — it must contain the primary keyword
4. After the title tag, the H1 heading and the first paragraph are most important
5. Content quality and user experience come first — keyword usage is a refinement, not the goal

---

## Phase 9: CSS, Semantic Markup, and Code Quality

These are indirect ranking factors — they affect how well engines parse and understand content, not directly how they rank it.

### CSS best practices with SEO implications

- Store CSS in external files — reduces HTML page weight, improves load speed, lowers abandonment
- Use tableless CSS layouts — cleaner semantic structure is easier for crawlers to parse
- Keep JavaScript calls external — reduces page weight
- Separation of presentation layer (CSS) from content layer (HTML) means the content the crawler sees is not obscured by layout code
- Use relative font sizes so users can resize text — usability and accessibility signals

### Code-to-text ratio

Reducing code bloat (excessive HTML, inline CSS, JavaScript) increases the ratio of indexable content to total file size. This is most impactful on very large sites with thousands of pages, where cumulative effects on crawl speed and page load times matter.

### Semantic markup

Using HTML elements semantically (headings as headings, not for visual styling; lists as lists; quotes as `<blockquote>`) helps engines parse document structure correctly. A common failure: using CSS to make paragraph text look large and bold (instead of using `<h2>`), so the engine sees no heading structure at all.

---

## On-Page SEO Audit Output Format

When delivering an on-page SEO audit, use this structure:

```
## On-Page SEO Audit: [Page URL or Site Section]

### Page: [URL]
Target keyword: [primary keyword]
Current title tag: [existing title] ([character count])
Current H1: [existing H1]
Current meta description: [existing description] ([character count])

### Issues found
[List: element — issue — severity (Critical / High / Medium / Low)]

### Recommended changes
Title tag: [proposed new title] ([character count])
H1: [proposed new H1]
Meta description: [proposed new description] ([character count])
URL (if changeable): [proposed URL]
Content gaps: [what topics/keywords are missing from the body]
Internal linking: [what pages should link to this one using what anchor text]

### Cannibalization check
[Are any other pages on the site competing for the same keyword? If yes, which page should be canonical?]
```

---

## Common Traps to Call Out

Proactively flag these when they appear in the user's situation:

- **Brand name at the start of every title tag** — unless the brand is dominant and recognition drives clicks, keywords should lead; brand should trail
- **Keyword stuffing** — repeating a phrase 15+ times in body content no longer helps ranking and can trigger quality filters; natural usage at 2–5 instances per 500 words is sufficient
- **Missing alt quotes** — `<img alt=keyword phrase>` (without quotes) passes only the first word to search engines; always use double quotes
- **One H1 per page being ignored** — either missing entirely or multiple H1s diluting the signal
- **Meta descriptions duplicated across pages** — near-duplicate metas are a thin content signal; either write unique ones or omit them
- **Title tags over 65 characters** — truncated in SERPs and potentially given lower weight; audit and trim
- **URLs with dates, session IDs, or tracking parameters** — pollute the index and create duplicate content
- **Keyword cannibalization left unresolved** — two competing pages will both rank poorly; consolidation almost always improves performance for both terms
- **Thin location pages** — changing only the city name across 100 template pages does not produce unique content; search engines recognize this and may filter all variants
- **Treating on-page optimization as a one-time task** — content ages, search intent shifts, competitors improve; on-page optimization is ongoing, not a one-time checklist
