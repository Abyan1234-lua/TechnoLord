# Duplicate Content & Crawl Control Reference

*Sourced from: The Art of SEO — Enge, Spencer, Fishkin & Stricchiola (Ch. 6 & Ch. 10)*

---

## Why Duplicate Content Hurts SEO

When the same (or very similar) content appears at multiple URLs:

1. **Link equity is split** — external sites linking to both versions dilute the authority that should concentrate on one URL
2. **Crawl budget is wasted** — crawlers spend quota visiting duplicate pages instead of unique content
3. **Wrong version may be indexed** — Google may select a version you don't want as the canonical, or show an unexpected URL in SERPs
4. **Algorithmic trust can drop** — a high proportion of duplicate pages relative to total pages signals low-quality content to Google's quality algorithms

---

## Duplicate Content Source Map

### Internal Duplication

```
Root cause               → URLs affected                    → Fix
─────────────────────────────────────────────────────────────────────────
www vs non-www           → domain.com AND www.domain.com    → 301 redirect
HTTP vs HTTPS            → http:// AND https://             → 301 redirect
Trailing slash           → /page AND /page/                 → 301 redirect
index.html               → /page/ AND /page/index.html      → 301 redirect
Session IDs              → /page?sess=abc AND /page?sess=xyz → Strip from URLs; use cookies
Tracking parameters      → /page AND /page?utm_source=email → Canonical tag or strip in GSC
Faceted navigation       → /shoes?color=red&size=10 × ∞    → Canonical + noindex
Pagination               → /category/page/1 through /N     → rel=next/prev
Sort orders              → /products?sort=price_asc        → Canonical to default sort
Print versions           → /page/print                     → Canonical to original
CMS archive types        → Tag + Date + Author + Category  → noindex low-value archives
```

### External Duplication

```
Root cause               → Example                          → Fix
─────────────────────────────────────────────────────────────────────────
Scrapers / content theft → Your article on spam domain     → DMCA; disavow if spammy links
Syndicated content       → Your post on partner site       → Canonical on partner pointing back to you
Press releases           → Article on newswires            → Canonical on wire to your site (if possible)
Manufacturer descriptions → Same product copy on 100 sites → Write unique descriptions
```

---

## Crawl Control Toolkit

Three tools for controlling what search engines crawl and index. Understanding their differences prevents catastrophic errors.

### 1. `robots.txt` — Controls Crawling

**What it does:** Tells bots whether they are *allowed to visit* a URL.

**What it does NOT do:** Prevent a URL from being indexed. If another site links to a disallowed page, it may still appear in the index.

```
User-agent: *
Disallow: /admin/
Disallow: /checkout/
Disallow: /search?
Allow: /
Sitemap: https://www.yourdomain.com/sitemap.xml
```

**Critical warning:** `Disallow: /` blocks ALL crawling of the entire site. This is a common catastrophic error during staging/dev deployments that accidentally go live.

**What to disallow:**
- Admin and CMS backend pages
- Checkout and cart pages
- Internal search results pages
- User profile pages
- Staging or test directories

**What NOT to disallow:**
- CSS and JS files (Google needs to render pages to evaluate them)
- Important content pages
- XML sitemaps

### 2. `meta robots` Tag — Controls Indexation

**What it does:** Tells bots whether to *include a page in the index* and whether to *follow links on it*.

**What it does NOT do:** Prevent crawling. `noindex` pages are still visited by bots.

```html
<!-- Default: crawl and index this page and follow its links -->
<meta name="robots" content="index, follow">

<!-- Exclude page from index; still crawl and follow links -->
<meta name="robots" content="noindex, follow">

<!-- Index page but do not follow links (rarely useful) -->
<meta name="robots" content="index, nofollow">

<!-- Exclude from index AND don't follow links -->
<meta name="robots" content="noindex, nofollow">
```

**`noindex` good candidates:**
- Faceted navigation / filter pages with no unique content
- Paginated archive pages beyond page 2
- HTML sitemaps (keep these to pass link juice; add noindex only)
- Thank-you / confirmation pages
- Printer-friendly page variants
- Internal search result pages

**`nofollow` (meta tag) warning:** Applying `nofollow` on a meta tag disables link juice from *all* links on that page. Per Google's Matt Cutts (2009): link juice is discarded, not redistributed. Using `nofollow` on internal links to sculpt PageRank is not effective and can be counterproductive.

### 3. `rel="canonical"` — Controls Which URL Gets Credit

**What it does:** Tells search engines which version of a URL should receive all link equity and appear in the index.

**What it does NOT do:** Prevent the page from being crawled. It's a hint, not a directive.

```html
<!-- On a duplicate or variant page, point to the master version -->
<link rel="canonical" href="https://www.yourdomain.com/master-page/" />
```

**When canonical ≠ 301:**

A 301 redirect is a stronger signal. Canonical is useful when:
- You need the variant URL to remain accessible to users for analytics or UX reasons
- You cannot implement server-side redirects (e.g., SaaS platforms)
- You're managing cross-domain syndication

**Canonical tag audit checklist:**
```
□ Every page has a self-referential canonical
□ All canonicals point to HTTPS URLs
□ Paginated series do NOT all point canonical to page 1
□ Variant/filter URLs point canonical to the base product/category page
□ Canonicals do not point to redirected URLs (canonical → 301 → final is wasteful)
□ Canonical tags are in the <head>, not the <body>
□ No pages with conflicting canonical signals (canonical + noindex pointing in different directions)
```

---

## Session IDs & Cookies

Session IDs appended to URLs create one of the most severe duplicate content problems at scale:

```
/product/red-shoes?sess=abc123
/product/red-shoes?sess=def456
/product/red-shoes?sess=ghi789
```

Each visit by a bot generates a new session ID. Google sees thousands of "unique" URLs — all containing identical content. This wastes crawl budget and may dilute rankings.

**Fix:**
- Store session data in cookies, not URL parameters
- If URL-based sessions are unavoidable, use the GSC URL Parameters tool to tell Google to ignore the session parameter
- Add a canonical tag on all session-ID variants pointing to the clean URL

---

## Pagination Best Practices

Pagination is one of the most common sources of both duplicate content and wasted crawl budget.

**Common mistakes:**
- All paginated pages share the same `<title>` and meta description as page 1
- Page 1 content (intro text, category description) is repeated on all pages
- Paginated pages all have `rel="canonical"` pointing to page 1 (removes them from index entirely)

**Correct implementation:**
- `rel="prev"` / `rel="next"` signals the sequence to Google
- Each page has a unique `<title>` (e.g., "Running Shoes - Page 2 of 12")
- Unique content (or at least different products/posts) on each page — no repeat of page 1 intro
- Consider `noindex` on pages beyond page 2 if they have very thin content

---

## Content Freshness & Crawl Frequency

Google recrawls content based on signals of freshness. Help it by:

- Including `<lastmod>` dates in your XML sitemap (set to the actual last modification date — do not fake it; Google detects this)
- Publishing updates and new content consistently
- Using `<changefreq>` hints in your sitemap (Google treats this as advisory, not binding)
- Ensuring your sitemap is resubmitted or auto-pinging after significant updates

Do not remove seasonal content after the season ends. Keep the URL live with updated content for next year — URLs with ranking history outperform new URLs every time.
