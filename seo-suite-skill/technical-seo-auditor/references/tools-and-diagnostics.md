# Tools & Diagnostics Reference

*Sourced from: The Art of SEO — Enge, Spencer, Fishkin & Stricchiola*

---

## Indexation & Crawl Diagnostics

| Tool | Purpose | Notes |
|---|---|---|
| `site:yourdomain.com` | Estimate indexed pages in Google / Bing | Not precise; use as a directional signal |
| Google Search Console | Accurate indexation data, crawl errors, manual actions, crawl rate | Primary source of truth for Google-specific data |
| Bing Webmaster Tools | Bing-specific indexation and crawl data | Use `IP:address` to check blocked IP ranges |
| Server logfile analyzers (AWStats, Webalizer) | Record every bot request including spider activity | JavaScript analytics cannot capture bot crawls |
| Screaming Frog SEO Spider | Full site crawl — finds broken links, missing tags, redirect chains, duplicate content | Industry standard for on-site technical audits |
| Google Search Console robots.txt Tester | Validate your robots.txt file after any change | Critical — always test before deploying changes |

---

## Server & HTTP Header Tools

| Tool | Purpose |
|---|---|
| Live HTTP Headers (Firefox extension) | Inspect HTTP response codes on any URL |
| httpstatus.io | Check status codes and redirect chains for any URL |
| Netcraft (netcraft.com) | Identify server software, hosting provider, server geography, historical data |
| GTmetrix / Google PageSpeed Insights | Diagnose page load time and rendering performance |
| Pingdom | Uptime monitoring and page load testing |

---

## Duplicate Content & Canonical Diagnostics

| Tool | Purpose |
|---|---|
| Screaming Frog — Duplicate Content report | Identifies duplicate title tags, descriptions, and near-duplicate page content |
| Google Search Console — Coverage report | Shows indexation status; identifies excluded pages, noindex pages, and redirect issues |
| Siteliner (siteliner.com) | Identifies internal duplicate content and broken links |
| Copyscape | Detects external duplicate content (your content appearing on other domains) |

---

## Competitor & Link Analysis

| Tool | Purpose |
|---|---|
| `site:www.competitor.com` | Rough indexed page count and title tag review for any competitor |
| Alexa, Compete, Quantcast | Estimate competitor traffic (directional only; not precise) |
| Google Trends for Websites | Compare relative traffic across multiple domains |
| Wayback Machine (archive.org) | Historical snapshots of any site — useful for understanding what changed and when |
| Ahrefs, Majestic, Moz | Backlink profile analysis for site and competitor comparison |

---

## Keyword & Rankings Diagnostics

| Tool | Purpose | Caution |
|---|---|---|
| Google Search Console — Performance | Actual clicks, impressions, CTR, and average position by query | Most reliable ranking signal from Google |
| Rank trackers (Semrush, Ahrefs, etc.) | Track keyword ranking trends | Rankings vary by geography, personalization, and data center; use as trends, not absolutes |
| Google Trends | Seasonal and trending keyword demand | Not keyword-level volume data |
| KeywordDiscovery | Historical keyword demand and seasonal trends | Good for planning content launch timing |

---

## XML Sitemap Tools

| Tool | Purpose |
|---|---|
| XML-Sitemaps.com Generator | Auto-generate XML sitemaps from crawl |
| Google Search Console — Sitemaps | Submit and monitor sitemap status; see URLs discovered and indexed |
| Screaming Frog | Generate XML sitemap from crawl output |

---

## Redirect & URL Rewrite Reference

### Apache `.htaccess` — key patterns

```apache
# Force HTTPS
RewriteEngine On
RewriteCond %{HTTPS} off
RewriteRule ^(.*)$ https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]

# Force www
RewriteCond %{HTTP_HOST} !^www\. [NC]
RewriteRule ^(.*)$ https://www.%{HTTP_HOST}/$1 [L,R=301]

# 301 redirect a specific old URL to a new one
Redirect 301 /old-page/ https://www.yourdomain.com/new-page/

# Redirect index files to root
RewriteRule ^(.*?)/?index\.html$ /$1/ [L,R=301]
```

> **Important:** Always use `R=301` for permanent redirects. `R=302` (the default when no flag is specified in some configurations) will NOT pass link equity.

### Checking redirect chains

1. Use httpstatus.io or Screaming Frog to trace the full redirect path for any URL
2. Flag any chain longer than 1 hop (old → final)
3. Update all internal links to point directly to the final destination URL
4. Consolidate chains: `A → B → C` should become `A → C` and `B → C`

---

## CMS-Specific SEO Audit Checklist

### WordPress

- [ ] Yoast SEO or RankMath installed and configured
- [ ] Custom permalinks set (not `?p=123` format)
- [ ] No `noindex` checkbox accidentally enabled on key pages
- [ ] Pagination handled correctly (`rel="next"` / `rel="prev"` or using Yoast pagination settings)
- [ ] Category/tag archive pages reviewed for thin content (consider `noindex` on low-value ones)
- [ ] XML sitemap generated and submitted to Search Console
- [ ] Duplicate content from multiple archive types (date/author/category) mitigated

### Magento / WooCommerce

- [ ] Faceted navigation / layered navigation URLs managed (canonicalize or `noindex`)
- [ ] Product variants (size/color) handled via canonical to parent product
- [ ] Pagination on category pages handled correctly
- [ ] Duplicate product pages from multiple category paths canonicalized
- [ ] Site speed optimized (e-commerce CMSs are notoriously heavy)

---

## Baseline Measurement Setup

Before beginning any SEO work, record these baselines:

| Metric | How to measure | Frequency |
|---|---|---|
| Indexed page count | `site:` search + GSC Coverage report | Monthly |
| Crawl rate | GSC Crawl Stats report | Monthly |
| Organic clicks & impressions | GSC Performance report | Weekly |
| Top organic landing pages | GSC Performance → Pages | Monthly |
| Keyword rankings for priority terms | Rank tracker | Weekly |
| Backlink count | Ahrefs / Majestic | Monthly |
| Page load time (homepage + key pages) | GTmetrix | Monthly |
| Crawl error count | GSC Coverage → Errors | Weekly |

> Note on rank tracking: Rankings vary by geography, personalization, and data center. Never use raw rank position as the primary KPI. Use organic click volume from GSC as the primary ranking proxy.
