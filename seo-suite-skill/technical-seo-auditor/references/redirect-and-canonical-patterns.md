# Redirect & Canonical Patterns Reference

*Sourced from: The Art of SEO — Enge, Spencer, Fishkin & Stricchiola (Ch. 6: Developing an SEO-Friendly Website)*

---

## The 301 vs. 302 Decision Tree

```
Is this move permanent?
├── YES → Use 301 (Moved Permanently)
│         ✓ Passes link equity to new URL
│         ✓ Old URL removed from index, new URL replaces it
│         ✓ Correct for: domain migrations, URL restructures, 
│           www/non-www consolidation, HTTP → HTTPS, CMS changes
│
└── NO  → Use 302 (Moved Temporarily)
          ✗ Does NOT pass link equity
          ✗ Old URL stays in index
          ✓ Correct for: A/B testing, maintenance redirects,
            genuinely temporary campaigns
```

**When in doubt: use 301.**

---

## Common Redirect Scenarios

### 1. WWW / Non-WWW Canonicalization

Pick one version. Redirect all traffic from the other.

```apache
# Redirect non-www to www (Apache .htaccess)
RewriteEngine On
RewriteCond %{HTTP_HOST} !^www\. [NC]
RewriteRule ^(.*)$ https://www.%{HTTP_HOST}/$1 [L,R=301]
```

Also set your preferred domain in Google Search Console.

---

### 2. HTTP → HTTPS Redirect

```apache
# Force HTTPS (Apache .htaccess)
RewriteEngine On
RewriteCond %{HTTPS} off
RewriteRule ^(.*)$ https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]
```

Verify: after implementing, confirm HTTPS is also the canonical URL in all `<link rel="canonical">` tags.

---

### 3. Index File Redirect (Prevent Duplicate Home Page)

Problem: `www.domain.com/` and `www.domain.com/index.html` are treated as two separate URLs.

```apache
# Redirect index.html to root (without infinite loop)
# Step 1: Create a new file (sitehome.php) with the content of index.php
# Step 2: Set DirectoryIndex to sitehome.php in .htaccess:
DirectoryIndex sitehome.php

# Step 3: Redirect the old index file
RewriteRule ^(.*?)/?index\.html$ /$1/ [L,R=301]
```

> The loop-avoidance technique (creating a separate sitehome.php) is necessary because setting a 301 from `/index.php` → `/` creates an infinite loop: the server loads `/` which requests `index.php` again.

---

### 4. Dynamic URL → Clean Static URL

When migrating from query-string URLs to SEO-friendly slugs:

```apache
# Map dynamic URL to clean URL (no redirect visible to user)
RewriteCond %{QUERY_STRING} id=([0-9]+)
RewriteRule ^get_product\.php$ /products/%1.html? [L,R=301]
```

After the migration: also update all internal links to use the new clean URLs, then 301 the old dynamic URLs.

---

### 5. Removing Tracking Parameters from Canonical URL

Tracking parameters (`?source=email`, `?utm_campaign=spring`) create URL variants that engines see as separate pages.

```apache
# Drop source parameter, redirect to clean URL
RewriteCond %{QUERY_STRING} ^source=[a-z0-9]*$
RewriteRule ^(.*)$ /$1? [L,R=301]
```

The trailing `?` in the destination drops the query string entirely.

---

### 6. Bulk URL Migration (Site Redesign)

When an entire site's URL structure changes:

1. Export old URL list from server logs / crawl tool
2. Map each old URL to its new equivalent (1:1 mapping preferred)
3. Implement 301 redirects for every changed URL — do not redirect all old URLs to the homepage
4. Verify redirect chain is a single hop: old → new (not old → intermediate → new)
5. Update XML sitemap to list new URLs only
6. Submit updated sitemap in Google Search Console
7. Monitor GSC Coverage report for crawl errors over the following 4–8 weeks

---

## Canonical Tag Patterns

### Self-referential canonical (recommended on all pages)

Every page should have a canonical tag pointing to itself. This prevents any accidental duplicate from being attributed.

```html
<head>
  <link rel="canonical" href="https://www.yourdomain.com/current-page/" />
</head>
```

### Consolidating duplicate product/page variants

E-commerce: `/products/red-shoes` and `/products/shoes?color=red` both exist.

On the variant page (`/products/shoes?color=red`):
```html
<link rel="canonical" href="https://www.yourdomain.com/products/red-shoes/" />
```

### Paginated series (use next/prev, not canonical to page 1)

Do **NOT** point all pagination pages to page 1. Instead:

Page 2 of a series:
```html
<link rel="prev" href="https://www.yourdomain.com/blog/" />
<link rel="next" href="https://www.yourdomain.com/blog/page/3/" />
```

Page 1:
```html
<link rel="next" href="https://www.yourdomain.com/blog/page/2/" />
```

Last page:
```html
<link rel="prev" href="https://www.yourdomain.com/blog/page/n-1/" />
```

### Cross-domain canonical (use case: syndicated content)

If your content is syndicated to another domain and you want to ensure your original version is treated as canonical:

On the syndicated copy (on the other domain):
```html
<link rel="canonical" href="https://www.youroriginaldomain.com/original-article/" />
```

Note: cross-domain canonicals are supported by Google but are a weaker signal than a 301 redirect.

---

## Canonical vs. 301: Choosing the Right Tool

| Scenario | Use 301 | Use Canonical |
|---|---|---|
| Permanently moved page | ✓ | ✗ |
| Domain migration | ✓ | ✗ |
| www / non-www consolidation | ✓ | ✗ |
| URL parameter variants you can't eliminate server-side | ✗ | ✓ |
| Faceted navigation URLs | ✗ | ✓ |
| Syndicated content on another domain | ✗ (if you control the other site) | ✓ |
| Pagination (beyond page 1) | ✗ | ✗ (use next/prev) |
| Print-friendly page variants | ✗ | ✓ |

---

## Redirect Audit Checklist

```
□ All permanent moves return 301, not 302
□ www → non-www (or vice versa) canonical redirect in place
□ HTTP → HTTPS redirect in place
□ No redirect chains longer than 1 hop
□ No redirect loops
□ /index.html and /index.php variants redirect to root
□ All old URLs from prior migrations still redirect (not 404)
□ HTTPS version has correct canonical tags
□ No internal links pointing to redirected URLs (update to point to final destination)
□ XML sitemap lists only canonical final URLs
□ 404 pages return genuine 404 status codes (not soft 404s returning 200)
```
