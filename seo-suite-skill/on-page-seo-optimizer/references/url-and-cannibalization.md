# URL Optimization & Cannibalization Reference

*Sourced from: The Art of SEO — Enge, Spencer, Fishkin & Stricchiola (Ch. 6: Developing an SEO-Friendly Website)*

---

## URL Optimization Checklist

```
□ URL describes the content (not a number or parameter string)
□ Words separated by hyphens (not underscores, not spaces, not camelCase)
□ All lowercase characters
□ No unnecessary folders or path segments
□ No tracking parameters (utm_source, utm_campaign, etc.) in the canonical URL
□ No session IDs
□ No dynamic query strings in canonical (? & = in the URL)
□ Keyword present in URL slug where natural (not forced)
□ URL is as short as possible while remaining descriptive
□ Consistent format across all pages in the same section
□ No uppercase letters (Unix/Linux servers are case-sensitive; uppercase creates duplicate URLs)
```

---

## URL Structure Examples

### Good URLs

```
/cordless-drills/                          ← Clean category
/cordless-drills/dewalt-20v-max/          ← Product with brand + model
/blog/how-to-choose-a-cordless-drill/     ← Blog post with keyword
/locations/austin-texas/                   ← Location page
/about/                                    ← Simple, short secondary page
```

### Bad URLs (and why)

```
/p?id=4728                    ← No content description; loses keyword signal
/Products/Drills/              ← Uppercase creates duplicate URL risk on Linux servers
/products/category/sub/items/drills/  ← Too many folder levels; unnecessary depth
/blog/2024/03/19/1042/         ← Date-based + ID; keyword completely absent
/drill?sess=abc123&ref=home&utm_source=email  ← Parameters in canonical
/buy-cheap-cordless-drills-online-best-price-free-shipping.html  ← Keyword spam
/page1/ /page2/ /page3/        ← No content signal at all
```

### URL rewrite examples (Apache mod_rewrite)

```apache
# Clean up dynamic product URLs
RewriteCond %{QUERY_STRING} id=([0-9]+)
RewriteRule ^product\.php$ /products/%1/ [L,R=301]

# Remove tracking parameters from canonical
RewriteCond %{QUERY_STRING} ^utm_source=
RewriteRule ^(.*)$ /$1? [L,R=301]

# Remove session IDs
RewriteCond %{QUERY_STRING} ^sess=[a-z0-9]+$
RewriteRule ^(.*)$ /$1? [L,R=301]
```

---

## Domain Name Selection Checklist

For new domain names or rebrands:

```
□ No hyphens (hard to say verbally; associated with spam)
□ No numbers (ambiguous: 4 or "four"?)
□ .com available and registered (most users default to .com type-in behavior)
□ Easy to spell correctly on first try
□ Easy to remember after hearing it once
□ Does not closely resemble a competitor or major brand
□ No trademark infringement (check USPTO before buying)
□ Under ~15 characters where possible
□ Not named after a trend (Web 2.0 misspellings, excessive adjectives)
□ Passes the "radio test": if said aloud, is it unambiguous?
□ Passes the "business card test": would you be comfortable putting it on printed materials?
```

### TLD selection guidance

| Situation | Recommendation |
|---|---|
| Commercial business (global or US) | `.com` — default choice |
| Country-specific business | `.co.uk`, `.de`, `.com.au` — only if serving that country exclusively and willing to forgo other markets |
| Nonprofit organization | `.org` may be appropriate |
| Government / military / educational | `.gov`, `.mil`, `.edu` — use these only if you actually qualify |
| All other cases | `.com` — `.net`, `.biz`, `.info` all have worse type-in rates and lower perceived trust |

---

## Keyword Cannibalization Diagnosis & Fix

### Step 1 — Build a keyword-to-page map

Create a spreadsheet:

| Target keyword | Intended page | Other pages ranking for this keyword |
|---|---|---|
| cordless drills | /cordless-drills/ | /blog/best-cordless-drills/ |
| best cordless drill | /blog/best-cordless-drills/ | /cordless-drills/ |
| dewalt cordless drill | /cordless-drills/dewalt-20v-max/ | /blog/dewalt-review/ |

### Step 2 — Identify conflicts

A conflict exists when:
- Two or more pages appear in the same column for the same keyword
- The intended page is NOT consistently ranking above the competitor page
- Rankings fluctuate between the two pages month to month

### Step 3 — Choose the canonical page

Criteria for choosing which page survives:

| Factor | Weight |
|---|---|
| More inbound links | High |
| More comprehensive content | High |
| Better keyword targeting (title, H1) | Medium |
| Higher traffic / conversion rate | Medium |
| More appropriate page type for the intent | High |

The page that better matches the searcher's intent for that keyword should be the canonical.

### Step 4 — Execute the consolidation

```
Option A — Merge and redirect (preferred when pages are similar):
1. Move all unique content from the weaker page into the canonical page
2. 301-redirect the weaker URL to the canonical page
3. Update all internal links from the weaker URL to the canonical URL

Option B — Reorient (when pages serve different intent):
1. Rewrite the weaker page to target a different, non-competing keyword
2. Update its title tag, H1, and body focus
3. Update internal links to use appropriate anchor text for the new keyword
```

### Step 5 — Update internal links

After choosing the canonical page, audit all internal links using the target keyword as anchor text and ensure they all point to the canonical page.

---

## Parent/Child Keyword Relationship Management

When your site has both a broad keyword page and a specific keyword page that contains the broad keyword:

```
Broad: "mortgages"          → Page: /mortgages/
Specific: "low-interest mortgages"  → Page: /mortgages/low-interest/
```

**Correct internal linking pattern:**
- The `/mortgages/low-interest/` page should link back to `/mortgages/` using the anchor text "mortgages"
- This link can appear in the breadcrumb (`Home > Mortgages > Low-Interest Mortgages`) or within the body copy
- This signals to search engines that `/mortgages/` is the authority on the broader term while `/mortgages/low-interest/` owns the specific variant

**Why it matters:**
Without this structure, both pages compete for the broad term. With it, each page has a clearly differentiated role — and internal link equity flows appropriately to reinforce that differentiation.

---

## Cannibalization Prevention at Scale

For large sites, prevent cannibalization proactively:

### Keyword map maintenance

- Maintain a master spreadsheet mapping every target keyword to its one assigned page
- When commissioning new content, check the map first — if the keyword already has a page, expand that page rather than creating a new one
- Review the map quarterly and resolve any new conflicts that have emerged

### CMS-level prevention

- Configure the CMS to show "existing pages targeting this keyword" when creating new content
- Use a tool like Semrush, Ahrefs, or Moz to run a cannibalization report quarterly
- Flag any two pages with title tags that contain 70%+ identical keywords

### Site architecture prevention

- Use a clear hub-and-spoke content model: one pillar page per topic, cluster pages for subtopics
- Each cluster page targets a more specific variant of the pillar keyword and links back to the pillar
- The pillar page links out to all cluster pages — this creates a clear signal hierarchy

```
Pillar: /cordless-drills/                    ← Targets "cordless drills"
  Cluster: /cordless-drills/18v/            ← Targets "18v cordless drill"
  Cluster: /cordless-drills/brushless/      ← Targets "brushless cordless drill"
  Cluster: /cordless-drills/dewalt/         ← Targets "dewalt cordless drill"
```

This architecture prevents cannibalization by design — each page has a clear, non-overlapping keyword role.
