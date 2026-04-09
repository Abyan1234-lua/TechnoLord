---
name: international-seo-planner
description: Plan and execute an international SEO strategy for websites targeting multiple countries or languages. Use this skill whenever the user wants to expand SEO to new countries or languages, set up hreflang tags, choose between ccTLDs/subdomains/subfolders, do keyword research in non-English languages, localize content for international search, diagnose why a site isn't ranking in a specific country, or plan global SEO at scale. Also trigger when the user says things like "expand to new markets", "why aren't we ranking in Germany", "should we use subfolders or subdomains for international", "hreflang implementation", "translate our site for SEO", or "how do we target multiple countries".
---

# International SEO Planner

Build an international SEO strategy grounded in real user demand — not geographic assumptions or machine-translated content.

The core principle: international SEO is not translation. It is building a product that users in a specific market want to find, in the language they actually search in, on a URL structure that signals local relevance to search engines. Most international SEO failures come from moving too fast, assuming too much, or treating regions as homogeneous blobs rather than distinct user populations.

---

## Step 1: Validate the international opportunity

Before any technical implementation, confirm demand actually exists. Expanding internationally without data is expensive and often wrong.

**Signals that international demand is real:**
- Analytics already shows meaningful traffic from target countries with reasonable engagement (not just bots)
- Google Search Console shows impressions from non-English queries related to your product
- Competitors in your space are visibly investing in the target market
- Your product already ships, serves, or is legally available in that market

**Red flags that suggest waiting:**
- Zero organic traffic from the target market today
- The product isn't available or usable in that country (payments, legal, language barriers)
- The team has no capacity to maintain localized content ongoing
- You're treating a language region ("Spanish") as a single market instead of individual countries

**How to estimate market size:**
- Use Google Search Console filtered by country to see existing impressions and queries
- Check competitor traffic estimates in the target country via tools (Ahrefs, Semrush, SimilarWeb)
- Search your core keywords in Google with the target country's locale — who's ranking? How strong are they?

> See [references/market-validation.md](references/market-validation.md) for a structured market-sizing worksheet.

---

## Step 2: Choose the right URL structure

This is the most consequential technical decision in international SEO. It cannot easily be undone. Choose once, and choose carefully.

### The three options

**Country-code top-level domains (ccTLDs)** — e.g., `example.de`, `example.fr`, `example.co.uk`

- Strongest geotargeting signal to search engines
- Best for conversion — local users trust and prefer local TLDs
- Requires: budget for domain registration and maintenance per country, local hosting strongly preferred, separate Google Search Console properties, and real local content (not just translated copy)
- Best for: companies with true local operations, large budgets, and long-term commitment to each market
- Risk: splitting link equity across domains from the start

**Subdomains** — e.g., `de.example.com`, `fr.example.com`

- Moderate geotargeting signal (can be set in Google Search Console)
- Can be hosted locally per subdomain (a real advantage)
- Link equity from main domain partially transfers
- Best for: companies with strong main domains, centralized marketing, limited local team but some local infrastructure
- Risk: search engines sometimes treat subdomains as separate sites; less effective than ccTLDs for pure country targeting

**Subfolders** — e.g., `example.com/de/`, `example.com/fr/`

- Weakest standalone geotargeting signal (relies on hreflang + GSC settings)
- Full benefit of main domain's link equity on day one
- Easiest to implement and maintain technically
- Best for: most companies, especially those starting out or with a strong existing domain
- Can set country geotargeting in Google Search Console
- Risk: harder to rank for very local queries without local hosting and ccTLD

### Decision framework

| Situation | Recommended structure |
|---|---|
| Starting international SEO, limited budget | Subfolders (`/de/`, `/fr/`) |
| Strong main domain, centralized team | Subfolders or subdomains |
| True local operations + long-term commitment | ccTLD |
| Single language, multiple countries (e.g., all Spanish) | Subfolders per country (`/mx/`, `/es/`, `/co/`) |
| Huge brand with existing ccTLDs | Maintain ccTLDs, apply hreflang |

**Never use IP-based redirection to serve different languages.** Search engine crawlers originate from US IP addresses — they will only ever see your US/English content, making all other language versions invisible to indexing.

---

## Step 3: Implement hreflang correctly

Hreflang is the signal that tells search engines which language/country version of a page to show to which user. It is widely misimplemented — get it right and it's a powerful signal; get it wrong and it creates ranking confusion.

### hreflang basics

Each page in your international setup needs a `<link rel="alternate" hreflang="[lang-country]">` tag pointing to every equivalent version of that page, including itself.

**Format:** `hreflang="[ISO 639-1 language]-[ISO 3166-1 country]"`

Examples:
- `hreflang="en-us"` — English for the United States
- `hreflang="de-de"` — German for Germany
- `hreflang="de-at"` — German for Austria
- `hreflang="es"` — Spanish (no country targeting — any Spanish speaker)
- `hreflang="x-default"` — fallback for users who don't match any other version

### Implementation rules

**Every page in the set must reference all other pages in the set — including itself.** A German page must reference the English page AND the German page. Asymmetric hreflang breaks the signal.

**Use absolute URLs, not relative paths.** `https://example.com/de/about/` not `/de/about/`.

**Include `x-default`.** This tells Google which page to show when no language/country match is found. Usually your default/English page.

**Three valid implementation methods (pick one per site, use consistently):**
1. HTML `<head>` link tags — most common, easiest to audit
2. HTTP headers — required for non-HTML files (PDFs, etc.)
3. XML Sitemap — good for large sites, but harder to maintain

**Common hreflang mistakes:**
- Pointing hreflang to redirected or non-canonical URLs
- Missing the self-referencing tag
- Using `hreflang="en"` when you mean `hreflang="en-us"` (these are different signals)
- Inconsistent implementation across site sections
- Not updating hreflang when URLs change

> See [references/hreflang-implementation.md](references/hreflang-implementation.md) for code templates and an audit checklist.

---

## Step 4: International keyword research

This is where most international SEO efforts go wrong. Direct translation of English keywords produces unnatural language that native speakers don't search — and Google's algorithm is less forgiving for non-English synonyms and spelling variants than it is for English.

### The right process (adapted from Eli Schwartz's field-proven approach)

1. **Start with translation candidates** — put your primary English keywords into Google Translate. Capture ALL translation possibilities, not just the first one. Single words and phrases often translate differently.

2. **Validate in a keyword tool** — run all translation candidates through a keyword volume tool (Ahrefs, Semrush, Google Keyword Planner) set to the target country. Volume alone doesn't mean usability — a high-volume term might be slang or have the wrong intent.

3. **Search the highest-volume candidates manually in Google** — in incognito, with locale set to the target country. Look at what's actually ranking. Who are your real competitors in that market?

4. **Study the ranking pages** — use two browser tabs: the original language version and Google Translate's rendering. Note the exact words used in title tags, H1s, navigation menus, and calls to action. Do this for every competitor result, including Wikipedia. These are the terms real speakers use.

5. **Build a target keyword list from what you find in step 4** — these are native-validated terms, not machine translations.

6. **Native speaker review is not optional** — before publishing, have a native speaker from the target country (not just the language — a Mexican Spanish speaker shouldn't review Argentina-targeted content) review all keywords and copy for naturalness, register, and local cultural fit. Hire via Upwork, Fiverr, or a local agency.

7. **Implement and track** — set up Google Search Console for the international property. Monitor rankings and iterate.

### Language ≠ country — treat each market distinctly

- Spanish in Spain, Mexico, Colombia, and Argentina uses different vocabulary and tone
- Portuguese in Brazil and Portugal have significant differences
- French in France vs. Canada vs. Belgium has meaningful variations
- Do not use one keyword list across multiple Spanish-speaking countries — validate per country

---

## Step 5: Content strategy for international markets

International content is not translation — it is localization. The distinction matters.

**Translation:** converting words from one language to another
**Localization:** adapting content to feel native — including cultural references, local examples, units, currencies, date formats, legal requirements, and local intent nuances

### Localization depth — choose a tier per market

| Tier | What it means | When to use |
|---|---|---|
| Tier 1 (Full) | Native-written content, unique per market, culturally adapted | Top-priority markets with strong demand |
| Tier 2 (Adapted) | Translated base, with local examples, references, and CTA adaptation | Mid-priority markets |
| Tier 3 (Translated) | Machine or professional translation, minimal local adaptation | Low-priority or exploratory markets |

**Never use Tier 3 content as a long-term strategy for a market you care about.** Google can identify machine-translated content, and users bounce from content that doesn't feel native.

### What must be localized beyond the words

- Currency and pricing (show local currency, not just converted USD)
- Units of measure (metric vs. imperial)
- Date formats (DD/MM/YYYY vs. MM/DD/YYYY)
- Phone number formats and local contact options
- Legal disclaimers and terms relevant to local law
- CTAs (what works in the US often doesn't work elsewhere — "Get a demo" vs. "Request information")
- Social proof — local customer logos, local case studies, local testimonials

### Don't stereotype regions

There are no countries called "LatAm", "APAC", or "Europe" from an SEO perspective. A user in Colombia searches differently from a user in Argentina. A user in Germany has different expectations from a user in Austria. Do not serve the same content to entire regions and expect strong results.

---

## Step 6: Technical implementation checklist

Before launch, verify every item on this list per international property.

**Crawlability:**
- [ ] No IP-based geo-redirection blocking search engine crawlers
- [ ] All international pages linked from the site (not orphaned)
- [ ] XML sitemap includes all international URLs with correct hreflang annotations
- [ ] robots.txt not accidentally blocking international directories

**hreflang:**
- [ ] All pages include self-referencing hreflang tag
- [ ] All pages reference all other language/country equivalents
- [ ] `x-default` tag present pointing to default/fallback page
- [ ] Only canonical URLs used in hreflang (no redirecting URLs)
- [ ] Consistent implementation across the full site (not just home page)

**Google Search Console:**
- [ ] Separate GSC property created for each international property (ccTLD, subdomain, or subfolder)
- [ ] Geotargeting set in GSC for subfolder or subdomain properties
- [ ] Sitemaps submitted per property

**Content:**
- [ ] No duplicate content across language/country versions of the same page
- [ ] Canonical tags on international pages point to their own URL (not to the English version)
- [ ] Native speaker review completed for all target-language content
- [ ] Local contact information, address, and phone number on relevant pages

**UX signals:**
- [ ] Language selector visible and functional
- [ ] Correct currency, units, date formats per locale
- [ ] Local payment methods available (if e-commerce)

---

## Step 7: Ongoing measurement and iteration

International SEO requires market-by-market reporting. A single aggregate dashboard masks what's actually happening.

**Per-country metrics to track:**
- Organic sessions by country (Google Analytics or equivalent)
- Impressions and clicks by country (Google Search Console per property)
- Keyword rankings in target country's Google (use rank trackers set to correct locale)
- Bounce rate and engagement per language version — a high bounce rate signals a localization problem, not an SEO problem

**Common failure modes to monitor:**
- Hreflang errors surfacing in GSC (check regularly)
- English pages ranking for non-English queries (hreflang not working or missing)
- Duplicate content between language versions (canonical issues)
- Stale content in secondary markets (content was translated once and never updated)

---

## Traps and misconceptions to flag

Call these out proactively when they appear in the user's situation:

- **"We'll just auto-translate our English site"** — machine translation produces unnatural content that ranks poorly and converts worse. Minimum viable quality requires human review.
- **"Spanish is one market"** — it's 20+ countries with distinct vocabularies, cultures, and search behaviors.
- **"Our .com will rank everywhere"** — without ccTLDs or proper subfolders + hreflang, a .com domain is heavily US-associated and will struggle to rank in local country searches.
- **"IP redirect users to their local version"** — this hides non-default language versions from search engine crawlers permanently.
- **"We ranked in English here, so the translation will rank too"** — ranking authority doesn't transfer across languages. A new language version starts from scratch in that language's competitive landscape.
- **"We'll do international SEO after the English site is perfect"** — the best time to add international infrastructure is during a site build or rebuild. Retrofitting is far more expensive.
