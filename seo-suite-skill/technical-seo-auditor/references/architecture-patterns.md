# Site Architecture Patterns Reference

*Sourced from: The Art of SEO — Enge, Spencer, Fishkin & Stricchiola (Ch. 6: Developing an SEO-Friendly Website)*

---

## The Filing Cabinet Mental Model

Think of a website the same way you think of a well-organized physical filing cabinet:

```
Filing Cabinet (Root Domain)
│
├── Drawer: Main Category A
│   ├── Folder: Subcategory A1
│   │   ├── Document: Product Page
│   │   └── Document: Product Page
│   └── Folder: Subcategory A2
│       └── Document: Article
│
└── Drawer: Main Category B
    ├── Folder: Subcategory B1
    └── Folder: Subcategory B2
```

Every document lives in exactly one place. Every path to reach it is clear. No dead ends.

---

## Flat vs. Deep Architecture

### Deep (problematic)

```
Homepage (click 1)
  └── Category (click 2)
       └── Subcategory (click 3)
            └── Sub-subcategory (click 4)
                 └── Product Page (click 5) ← buried from crawlers
```

Deep sites bury important pages from both users and crawlers. Each additional click level dilutes link equity flowing to those pages.

### Flat (recommended)

```
Homepage
├── Category A
│   ├── Product 1
│   ├── Product 2
│   └── Product 3
├── Category B
│   ├── Article 1
│   └── Article 2
└── Category C
    └── Landing Page 1
```

**Rule of thumb:** No page on a site with fewer than 10,000 pages should require more than 3 clicks from the homepage.

For sites with millions of pages: using category hubs with 100 links each, a 5–6 click maximum is achievable.

---

## Topic Cluster Architecture

Organize related content around pillar pages. This creates semantic relevance signals and concentrates link equity where it counts.

```
Pillar Page: /running-shoes-guide
  (broad topic, high authority)
  │
  ├── Cluster: /running-shoes-guide/trail-running-shoes
  ├── Cluster: /running-shoes-guide/road-running-shoes
  ├── Cluster: /running-shoes-guide/minimalist-shoes
  └── Cluster: /running-shoes-guide/how-to-choose-running-shoes
```

Internal linking rules for clusters:
- Each cluster page links back to the pillar
- The pillar links out to all cluster pages
- Cluster pages can link to related cluster pages within the same topic
- Do not link across unrelated topic clusters just for PageRank sculpting

---

## URL Structure Best Practices

Good URLs are:
- **Static-looking** — no session IDs, no random parameters
- **Keyword-bearing** — reflect the topic of the page
- **Hierarchical** — reflect the site's category structure
- **Stable** — once published, changing a URL requires a 301 redirect

| ❌ Poor URL | ✓ Good URL |
|---|---|
| `/p?id=4823` | `/products/mens-trail-running-shoes/` |
| `/page.php?cat=12&sub=44&item=234` | `/footwear/trail/salomon-speedcross/` |
| `/1920391029.html` | `/blog/how-to-choose-running-shoes/` |
| `/en/us/category/shoes` | `/shoes/` (if all users are English-speaking) |

**Keyword placement in URL matters.** Keywords closer to the domain root carry slightly more weight than those buried in subdirectories.

---

## Subdomain vs. Subfolder Decision Matrix

| Factor | Subfolder (`/blog/`) | Subdomain (`blog.domain.com`) |
|---|---|---|
| Link equity accumulation | All on root domain | Split; may not fully flow to root |
| Crawl efficiency | Single domain crawl budget | Separate crawl budget |
| Authority consolidation | Maximum — everything counts for the root | Partial — treated somewhat independently |
| Marketing flexibility | Less flexible for distinct brand identity | More flexible |
| Technical complexity | Simpler | Requires separate DNS, verification in GSC |
| **Default choice** | **✓ Always prefer if possible** | Only if genuinely needed |

**Rule:** Use a subfolder 99.9% of the time. The only valid reasons for a subdomain are when the content is genuinely separate in purpose (e.g., an app, a country-specific site with different language), or when marketing demands it and you can accept the SEO tradeoff.

---

## Site Architecture Design Process

Use this process when designing or auditing a site's architecture:

1. **List all required content pages** — product detail pages, category pages, blog posts, landing pages, support pages
2. **Create top-level navigation** — identify categories that can comfortably organize all content types
3. **Work bottom-up** — start with the most granular content and work toward the top to determine what hierarchy it fits in
4. **Fill in the middle** — build subcategory structure to logically connect top navigation with detail pages
5. **Include secondary pages** — contact, about, legal, sitemap (these should exist but do not need to be prominent in the hierarchy)
6. **Build a visual sitemap** — document the full structure down to at least the subcategory level before building

---

## Navigation Patterns to Avoid

| Pattern | Problem |
|---|---|
| JavaScript-only navigation | Links may not be crawled or weighted; provide HTML fallback |
| Flash navigation | Links inside Flash are invisible to most crawlers |
| Navigation behind a login | Content inaccessible to bots (and to unregistered users) |
| Cookie-gated navigation | Bots don't have cookies; will not see personalized nav |
| Session-ID URLs in navigation | Each bot visit generates a new, unique URL — creates duplicate content at scale |
| Frames/iframes for nav | Splits content across multiple URLs; creates link attribution confusion |
| Infinite pagination loops | Spider traps; bots get stuck following next/next/next indefinitely |
| AJAX content with # fragments | Everything after `#` is ignored by search engines |

---

## Internal Linking Guidelines

Internal links distribute link equity ("link juice") throughout the site. Architecture determines how that juice flows.

**Key principles:**
- Pages linked from the homepage receive the most link equity
- Pages only reachable from 4+ clicks deep receive very little link equity
- Anchor text on internal links sends relevance signals — use descriptive keywords, not "click here"
- Do not use `rel="nofollow"` on internal links to sculpt PageRank — Google discards that link juice rather than redistributing it (confirmed by Google's Matt Cutts)
- Link between pages with related content — this reinforces topical relevance signals

**Practical limits:**
- Maximum ~100 outbound links per page (Google's advisory)
- Very important pages (deeply linked-to from external sources) may accommodate up to 150–200

---

## E-Commerce Architecture Considerations

Large e-commerce sites have unique architecture challenges:

| Challenge | Solution |
|---|---|
| Thousands of product variants (size/color) | Canonical tag on each variant pointing to the master product page |
| Faceted navigation creating thousands of filter URLs | Canonical tags + `noindex` on low-value filter combinations |
| Products appearing in multiple categories | Single canonical URL per product; use breadcrumbs to reflect category context |
| Paginated product listings | `rel="next"` / `rel="prev"` on paginated category pages |
| Out-of-stock product pages | Keep the URL live; update content; do not 301 to category page unless permanently discontinued |
| Seasonal products removed | 301 to most relevant category or a replacement product |

---

## Taxonomy and Ontology

**Taxonomy:** the hierarchical classification of content (the 2D tree structure of your site)

**Ontology:** the full map of relationships between concepts, including cross-category connections that don't fit into a strict hierarchy

For SEO, a well-designed ontology means:
- Related pages link to each other even across different branches of the hierarchy
- Search engines can infer topical authority because related content is clustered and cross-linked
- Users can navigate between related topics without returning to a top-level category

**Card sorting** is a practical technique: write concepts on cards, have test users group them, and use the results to validate (or correct) your proposed hierarchy before building it.
