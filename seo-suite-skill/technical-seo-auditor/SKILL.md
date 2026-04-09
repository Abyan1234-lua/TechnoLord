---
name: technical-seo-auditor
description: Perform a comprehensive technical SEO audit of any website. Use this skill whenever the user wants to audit a site for technical SEO issues, diagnose why a site isn't ranking or indexing properly, identify crawlability and spiderability problems, review site architecture, investigate redirect and canonicalization issues, surface duplicate content problems, check server/hosting configuration, or build a prioritized technical SEO fix list. Also trigger when users say "my site isn't ranking", "pages aren't being indexed", "we're migrating the site", "something dropped after a redesign", or "run a technical audit on our site."
source: The Art of SEO — Eric Enge, Stephan Spencer, Rand Fishkin & Jessie C. Stricchiola (O'Reilly Media, 2009)
---

# Technical SEO Auditor

Audit a website systematically for technical issues that prevent pages from being crawled, indexed, and ranked. A technical audit is always the first step before any content or link work — if the foundation is broken, everything built on top of it will underperform.

The core principle: **Search engine crawlers are software programs with specific strengths and limitations. Your job is to leverage their strengths and eliminate their weaknesses.**

---

## How to use this skill

Read the user's context before starting. Identify which phase is most relevant, then work through it in order. You can run the full audit end-to-end or focus on a single module based on the reported problem.

- **"We're starting SEO from scratch"** → Run all phases top to bottom
- **"Pages aren't showing in search results"** → Start at Phase 1 (Indexation) and Phase 3 (Robots/Sitemaps)
- **"Our rankings dropped after a redesign"** → Start at Phase 5 (Redirects) and Phase 2 (Architecture)
- **"We have duplicate content issues"** → Go directly to Phase 6
- **"Something's wrong with the server"** → Go to Phase 7
- **"We need a full pre-launch check"** → Run all phases as a checklist

---

## Phase 1: Indexation Health Check

The most basic question: **does Google know your site exists, and are the right pages in its index?**

### Quick indexation diagnostic

Run a `site:yourdomain.com` search in Google, Bing, and other target engines. Compare the result count to the number of unique, canonical pages you believe the site has.

Ask:
- Is the indexed page count dramatically lower than the total page count? → Crawl accessibility problem.
- Is the indexed page count dramatically *higher* than expected? → Duplicate content or parameter bloat.
- Are key landing pages, product pages, or category pages missing from results? → Crawl budget, robots block, or orphan pages.

### Tracking indexation over time

Keep a simple spreadsheet log of `site:` counts over time. A downward trend is a serious signal. An upward trend post-audit confirms that fixes are working.

### Crawl rate tracking

Use Google Search Console to review crawl rate and average time spent downloading pages. Short-term spikes are normal. A declining long-term crawl trend is a warning sign.

For non-Google engines, use server logfile analyzers to track spider activity. Logfiles capture what JavaScript analytics tools cannot — every request made by every bot.

> See [references/tools-and-diagnostics.md](references/tools-and-diagnostics.md) for recommended tools by category.

---

## Phase 2: Site Architecture & Crawl Accessibility

Architecture determines whether crawlers can reach and properly interpret every page on the site.

### The filing cabinet principle

Think of a website the same way you think of a well-organized filing cabinet. Every document lives in exactly one location. Every path to find it is clear and predictable. There are no dead ends.

Good architecture for SEO means:
- **Flat, not deep.** Every page should be reachable within 3 clicks from the homepage (or 5–6 on very large sites using proper link structures). Deep nesting buries pages from both users and crawlers.
- **100 links per page maximum.** Google has indicated it may stop following additional links beyond ~100 per page. Keep navigation and listing pages within this limit.
- **Logical, hierarchical flow.** Content should move from broad (homepage → categories) to narrow (subcategories → detail pages). Semantic proximity to a topic group signals topical authority.
- **One URL per piece of content.** Avoid multiple paths that resolve to the same content.

### Architecture audit checklist

| Issue | How to check | Priority |
|---|---|---|
| Pages not reachable via internal links ("orphan pages") | Crawl with Screaming Frog or similar; compare to sitemap | Critical |
| Navigation only in JS, Flash, or forms | View page source; disable JS and check nav | Critical |
| More than 3 clicks to reach important pages | Manual crawl path test | High |
| More than 100 links on key pages | Use a crawler or browser extension | High |
| iframes used for navigation content | View source | Medium |
| Navigation behind login or cookie wall | Test in incognito / with cookies disabled | High |

### What makes links uncrawlable

These constructs prevent or impede spiders from following links:

- **Submission-required forms** — spiders do not submit forms; any URL only reachable via a search box or login is invisible
- **JavaScript-only links** — links embedded purely in JavaScript may not be followed or may carry no weight
- **Flash/Java/plug-in links** — links inside Flash, Java applets, or browser plug-ins are effectively invisible
- **Links blocked by robots.txt or `rel="nofollow"`** — the engine will not follow or pass authority through these
- **Frame and iframe navigation** — frames split content across multiple URLs in ways that confuse indexing and attribution of links
- **Session IDs in URLs** — each spider visit gets a unique URL, which the engine treats as a separate (duplicate) page

### AJAX and dynamic content

If your site uses AJAX to load content without changing the URL, that content is largely invisible to search engines. The solution: build a parallel set of static, crawlable HTML pages with unique URLs and ensure those pages link to each other. Provide users with "direct link" options that lead to these crawlable URLs.

Do not use `#` fragments as page identifiers. Everything after `#` is ignored by search engines (it's processed by the browser locally and never sent to the server).

### Subdomain vs. subfolder decision

| Structure | Recommendation |
|---|---|
| **Subfolder** (`domain.com/blog/`) | Always prefer this. All authority, trust, and links earned accumulate on the root domain. |
| **Subdomain** (`blog.domain.com`) | Use only when marketing demands a clearly separate identity, or when the content is genuinely distinct in purpose. Note: links to a subdomain may not fully pass authority back to the root. |
| **Separate root domain** | Rarely justified. Splitting content across multiple domains splits link equity and forces you to rebuild all authority metrics from zero. |

> See [references/architecture-patterns.md](references/architecture-patterns.md) for site structure diagrams and decision trees.

---

## Phase 3: Robots.txt, Meta Robots & XML Sitemaps

### Robots.txt audit

The `robots.txt` file is among the most dangerous files on a site — a single typo can tell search engines to stop crawling the entire site.

**Always verify after any change** using Google Search Console's robots.txt tester.

Check for:
- Unintentional `Disallow: /` — blocks all crawling
- Accidental blocking of CSS/JS files (which hinders Google's ability to render pages)
- Blocking of key sections (e.g., `/products/`, `/category/`)
- Missing or misformed `User-agent` declarations
- Presence of the `Sitemap:` autodiscovery directive

**Robots.txt critical syntax:**
```
User-agent: *
Disallow: /private/
Disallow: /admin/
Sitemap: https://www.yourdomain.com/sitemap.xml
```

### Meta robots tag audit

Check every important page for `<meta name="robots">` tags, particularly:
- **`noindex`** — removes the page from the index entirely (the page is still crawled, can still pass link value, but will not appear in SERPs)
- **`nofollow`** — instructs crawlers not to follow links on this page (use with care; link juice is not redistributed)
- Unintentional `noindex` on key landing pages, category pages, or product pages is one of the most common and damaging technical SEO errors

Key distinction: `noindex` ≠ `disallow` in robots.txt.
- `Disallow` in robots.txt prevents crawling but does not prevent indexing (the page can still appear if linked from other sites).
- `noindex` in meta robots prevents indexing but the page continues to be crawled.

### XML Sitemap audit

A sitemap is a supplement to — not a replacement for — link-based crawling. It increases crawl coverage and helps search engines identify the canonical version of URLs.

**What to include:** Only canonical URLs. Never list pages with tracking parameters, pagination pages, low-value pages, or URLs you have blocked in robots.txt.

**What to exclude:** Duplicate URLs, paginated archive pages, session-ID URLs, admin/login pages.

Check:
- Is the sitemap referenced in robots.txt and submitted in Google Search Console?
- Does it include all strategic pages (product pages, key landing pages, category pages)?
- Are all listed URLs returning 200 status codes?
- Is the `<lastmod>` date accurate?
- Does the sitemap itself return a 200 status code?
- For large sites: are sitemap index files used to split into segments under 50,000 URLs each?

---

## Phase 4: On-Page Technical Elements

### Title tag audit

| Issue | Guidance |
|---|---|
| Missing title tag | Critical — every page must have one |
| Duplicate title tags | Critical — each page must have a unique title |
| Title over 60–70 characters | Gets truncated in SERPs; move keywords to the front |
| Brand name at front | Move to end; keywords at the start carry more weight |
| Generic/boilerplate titles ("Home", "Page 1") | Replace with descriptive, keyword-rich titles |

### Meta description audit

Meta descriptions do not directly affect ranking, but they affect click-through rate from SERPs and may factor into duplicate content calculations.

- Each page should have a unique meta description
- If uniqueness is not achievable at scale, consider removing meta descriptions on those pages rather than using identical ones
- Limit to ~155–160 characters
- Write them for humans; they function as ad copy

### Header tag audit

- Every page should have exactly one `<h1>` tag
- The `<h1>` should be the primary topic/keyword of the page — article title, product name, category name
- Low-value content (dates, author names) should not be wrapped in `<h1>`
- Multiple `<h2>` and `<h3>` tags are appropriate for subheadings
- Pages with no header tags at all are a missed opportunity

### Image alt attribute audit

Search engines cannot read the content of images. The `alt` attribute is the primary way to communicate image context.

- All images should have relevant, descriptive `alt` text
- Image filenames should also be descriptive (`red-running-shoes.jpg`, not `IMG_4732.jpg`)
- Do not keyword-stuff alt text; make it descriptive as if explaining the image to someone who cannot see it
- `alt` attributes on image links function as the anchor text for that link

### Content quality signals

- Identify pages with very thin content (a few sentences or less) relative to the total page count. A high ratio of thin pages to total pages is a trust and quality signal risk.
- Check for large sections of duplicated boilerplate text across pages (common in e-commerce templates).
- Ensure body content is in indexable HTML text — not embedded in images, Flash, or JavaScript.

---

## Phase 5: Redirects & Canonicalization

Redirects and canonicalization are among the most impactful — and most error-prone — areas in technical SEO.

### 301 vs. 302: the critical distinction

| Code | Meaning | SEO Impact |
|---|---|---|
| **301 — Moved Permanently** | Resource has permanently moved | Passes historical link equity to the new URL; old URL is removed from the index |
| **302 — Moved Temporarily** | Resource has temporarily moved | Does **not** pass link equity; old URL remains in the index |

**Always use 301 for permanent moves.** Using 302 by mistake for a permanent redirect means you lose all the accumulated link value of the old URL.

After any redirect chain: old URL → intermediate URL → final URL, link equity is diminished at each hop. Keep redirect chains to a single hop wherever possible.

### Redirect audit checklist

Use a server header checker tool (e.g., Screaming Frog, httpstatus.io, or browser extension Live HTTP Headers) to verify:

- All permanent redirects return 301, not 302
- The www/non-www canonical redirect is in place (domain.com → www.domain.com or vice versa — pick one and stick to it)
- `index.html` or `index.php` variants redirect to the root URL (`/index.html` → `/`)
- No redirect chains exceed 1–2 hops
- No redirect loops exist
- HTTPS → HTTP redirects are not present (HTTPS should be canonical)
- Old URLs from a site migration all resolve via 301 to relevant new equivalents

### Canonical tag audit

The `rel="canonical"` tag (introduced in 2009 by Google, Yahoo!, and Bing jointly) tells search engines which URL should be treated as the master version when multiple URLs contain the same or similar content.

```html
<link rel="canonical" href="https://www.yourdomain.com/canonical-page/" />
```

Key differences from a 301:
- Canonical tags redirect only bots, not human visitors — you can still track separate URL versions in analytics
- 301 is a stronger signal; canonical is a "hint" that engines may override if they disagree
- Canonical tags work within a single root domain (and subdomains); 301s can pass equity across domains

Common canonical errors:
- Pages canonicalizing to a URL that itself is not indexed
- Paginated pages all pointing to page 1 (this prevents pagination pages from being indexed; use `rel="next"` and `rel="prev"` for paginated series)
- Canonical tags pointing to non-HTTPS versions of pages
- CMS generating self-referential canonicals on every page (acceptable) vs. incorrect cross-page canonicals

**Best practice:** Fix the underlying duplicate content issue first. Use canonical tags as a secondary safety net, not as the primary solution.

> See [references/redirect-and-canonical-patterns.md](references/redirect-and-canonical-patterns.md) for `.htaccess` mod_rewrite examples and IIS redirect patterns.

---

## Phase 6: Duplicate Content Audit

Duplicate content dilutes link equity, wastes crawl budget, and can result in the wrong page version appearing in SERPs (or none at all).

### Common sources of duplicate content

| Source | Description |
|---|---|
| www vs. non-www | `www.domain.com/page` and `domain.com/page` treated as separate URLs |
| HTTP vs. HTTPS | `http://` and `https://` versions both live and indexed |
| Trailing slash variation | `/page` and `/page/` treated as separate URLs |
| `index.html` variant | `/page/` and `/page/index.html` both indexed |
| Session IDs in URLs | `/page?sessionid=abc123` creates thousands of "unique" URLs per real page |
| URL tracking parameters | `/page?source=newsletter` creates new URL for the same content |
| Faceted navigation / filtered sorting | `/products?color=red&sort=price` × every filter combination |
| Pagination | `/page/2`, `/page/3` showing the same introductory content repeated |
| CMS syndication | Same content appearing on permalink page, tag pages, category pages, date archives, and home page simultaneously |
| Scraped/syndicated content | Your content published on other domains |
| Print versions | `/page` and `/page/print` containing identical body content |

### Fixing duplicate content

Priority order of fixes:
1. **Resolve at the server level** — 301 redirect all duplicate variants to the canonical version. This is the strongest signal.
2. **Implement canonical tags** — for cases where you cannot redirect (e.g., filtered navigation where all filter combinations must remain accessible to users).
3. **Use `noindex`** — for low-value pages you want to keep accessible to users but remove from search (e.g., paginated archives beyond page 2, printer-friendly pages).
4. **Parameterization control** — use Google Search Console's URL Parameter tool to tell Google which parameters change content and which are decorative (e.g., tracking parameters).

For CMS-generated duplication (WordPress, Magento, etc.):
- Use unique excerpt text on archive/tag/category pages rather than repeating full content
- Apply `noindex` to low-value archive pages
- Ensure breadcrumb URLs match canonical URLs

---

## Phase 7: Server & Hosting Audit

Server problems are less frequent than on-page issues, but when they occur they can be catastrophic and are easy to overlook.

### Server issues that directly impact SEO

| Issue | Impact | Check |
|---|---|---|
| **Server timeouts** | Pages never make it into the index; pages that are indexed rank very poorly | Monitor uptime; check server logs for 5xx errors |
| **Slow response times** | Crawlers deprioritize slow sites; users bounce before links; rankings suffer | Google PageSpeed Insights, GTmetrix |
| **Shared IP with spam neighbors** | Risk of inheriting negative associations from penalized IP ranges | Check IP reputation; research shared hosting neighbors |
| **Blocked IP ranges** | If you're on an IP block associated with spam, crawlers may reduce or stop visiting | Search `IP:your.ip.address` in Bing |
| **Bot detection/rate limiting** | Overly aggressive bot-blocking settings stop crawlers cold | Review `.htaccess` and server security rules for bot throttling |
| **Bandwidth limitations** | When popular content spikes traffic, the host cuts access — preventing crawling and linking simultaneously | Monitor server access logs during high-traffic events |
| **Server geography** | Server location is a local search ranking factor; host where your primary audience is | Verify with hosting provider; check via Netcraft |

### HTTP status code audit

Every URL in your crawl should return one of:
- **200** — OK (content served)
- **301** — Permanent redirect (passes equity)
- **404** — Not found (acceptable for genuinely removed pages; do not 301 everything to the homepage)

Investigate any significant number of:
- **302s** on permanent redirects (should be 301s)
- **4xx errors** on pages still internally linked from the site
- **5xx errors** (server failures)
- **Soft 404s** — pages that return a 200 but display "page not found" content

---

## Phase 8: Crawl Budget Management (Large Sites)

For sites with thousands to millions of pages, Google allocates a finite "crawl budget" — a limit on how many pages it will crawl in a given period.

### Protect crawl budget by eliminating low-value URLs

Apply `noindex` or `disallow` (carefully) to:
- Thin or duplicate paginated pages beyond page 2
- Internal search result pages
- Filtered/faceted navigation URLs with no unique content
- Admin pages, login pages, checkout flow pages
- Low-value tag/archive combinations with minimal content

### Ensure important pages are reachable

- High-priority pages should be linked from the homepage or top-level navigation
- XML Sitemaps should list all strategic pages
- Pages deep in the architecture that are not linked to from anywhere are effectively orphaned

---

## Phase 9: CMS-Specific Technical Issues

CMSs introduce recurring patterns of technical SEO problems. Check for these:

| CMS Feature | What to Audit |
|---|---|
| Title tag generation | Can each page have a unique, manually customizable title? Does the CMS prepend the site name? |
| URL structure | Are URLs static and keyword-friendly? Do they avoid session IDs and query strings? Can slugs be customized? |
| Meta description control | Can each page have a unique meta description? |
| Canonical URL handling | Does the CMS auto-generate correct self-referential canonicals? Are there CMS-introduced duplicate URL variants? |
| 301 redirect support | Can 301 redirects be created within the CMS for changed/deleted pages? |
| Pagination handling | Does the CMS apply `rel="next"` / `rel="prev"`? Are archive/tag pages given `noindex` options? |
| Image alt attributes | Does the media library support alt text on all uploads? |
| H-tag control | Can editors set `<h1>` independently from `<title>`? |
| Feed/RSS generation | Are feeds auto-generated and properly formatted? |
| Robots.txt editability | Can the `robots.txt` be edited directly? |

---

## Phase 10: Penalties & Manual Actions

### Signs of a penalty or filter

- Sudden, significant drop in rankings across many keywords simultaneously (algorithmic filter)
- A specific page drops to the bottom of the index or disappears (page-level penalty)
- Traffic from a specific search engine drops to near-zero while others are unaffected
- `site:yourdomain.com` shows drastically fewer pages than before
- A manual action notification appears in Google Search Console

### Historical audit: previous SEO work

When auditing an existing site:
1. Check Google Search Console for manual actions
2. Review the site's history via the Wayback Machine (archive.org) — look for architectural and content changes that correlate with traffic changes
3. Audit the link profile for toxic, paid, or unnatural links (if link-building was done previously)
4. Identify any previous redirects, domain migrations, or URL structure changes that may not have been executed correctly

### Common spam filters

- Over-optimized anchor text in the link profile
- Keyword stuffing in title tags, headings, or body content
- Cloaking (showing different content to bots vs. humans)
- Doorway pages (thin pages designed purely for a specific keyword, redirecting users to a different destination)
- Paid link schemes
- Hidden text (white text on white background, text sized to zero, text hidden behind images)

---

## Audit Output Format

When delivering a technical SEO audit, use this structure:

```
## Technical SEO Audit: [Site Name]

### Executive Summary
[3–5 sentences: most critical issues, overall site health, recommended priority order]

### Critical Issues (fix immediately)
[List with: issue description, pages/URLs affected, specific fix recommendation, estimated effort]

### High-Priority Issues (fix within 30 days)
[Same format]

### Medium-Priority Issues (fix within 90 days)
[Same format]

### Monitoring Recommendations
[What to track in Search Console, what to log, what to check monthly]

### Quick Wins
[Changes that can be made in <1 day with meaningful impact]
```

---

## Priority Scoring Model

Use this to stack-rank findings for the client:

| Finding | Crawl Impact (1–5) | Index Impact (1–5) | Ranking Impact (1–5) | Effort to Fix (1=hard, 5=easy) | Score |
|---|---|---|---|---|---|
| Accidental noindex on key pages | 2 | 5 | 5 | 4 | 16 |
| 302 instead of 301 redirects | 3 | 4 | 4 | 4 | 15 |
| No XML sitemap | 4 | 3 | 2 | 5 | 14 |
| Duplicate title tags | 1 | 2 | 4 | 3 | 10 |

Sort by score descending. Present top 5–10 to client with clear ownership.

---

## Common Traps to Call Out

Proactively flag these when they appear in the audit:

- **Relying on `site:` count as an accurate index measure** — it's an estimate; use Search Console data for precise figures
- **Using 302 redirects for "permanent" page moves** — engineers often default to 302; always verify with a header checker
- **Blocking CSS/JS in robots.txt** — Google needs to render the page to understand it; blocking rendering resources hurts Googlebot's ability to evaluate the page
- **Canonicalling paginated pages to page 1** — this removes pagination pages from the index entirely; use `rel="next"` / `rel="prev"` instead
- **Treating noindex as a crawl block** — `noindex` pages are still crawled; only `Disallow` in robots.txt prevents crawling (but does not guarantee removal from the index)
- **Session IDs on public-facing pages** — each spider visit generates a unique URL; Google sees thousands of "unique" versions of the same page
- **Excessive redirect chains** — each hop in a chain reduces the link equity passed; consolidate chains to single 301s
- **Launching a site redesign without a redirect map** — every changed URL without a 301 is a dead end for all accumulated link equity and user bookmarks
