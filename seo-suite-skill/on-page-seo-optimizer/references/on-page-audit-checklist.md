# On-Page SEO Audit Checklist

*Sourced from: The Art of SEO — Enge, Spencer, Fishkin & Stricchiola (Ch. 6: Developing an SEO-Friendly Website)*

---

## Per-Page Audit Checklist

Run this for any individual page you are optimizing.

### Title Tag
```
□ Contains the primary target keyword
□ Keyword appears in the first 1–3 words (or as early as naturally possible)
□ Under 65 characters (including spaces)
□ Unique — not duplicated on any other page on the site
□ Brand name at the end (unless brand recognition drives click-through)
□ Matches the intent of the target query (research vs. purchase vs. navigational)
□ Compelling — written to earn the click, not just rank
□ Accurate — truthfully represents the page content
```

### Meta Description
```
□ Contains the primary keyword
□ Under 155 characters (including spaces)
□ Unique per page (or deliberately omitted for long-tail pages)
□ Reads like a concise ad for the page — specific, compelling, action-oriented
□ Matches searcher intent (not a sales pitch on an informational page)
□ Does not duplicate the title tag
```

### H1 Heading
```
□ Exactly one H1 per page
□ Contains the primary keyword
□ Appears early on the page (before any significant body content)
□ Represents the main topic — not a date, author name, or category label
□ Does not duplicate the title tag exactly (slight variation is fine)
□ Appropriate length — not a sentence fragment, not a paragraph
```

### H2 and H3 Headings
```
□ Logical hierarchy — H2 for main subtopics, H3 for sub-subtopics within H2 sections
□ No skipped heading levels (H1 → H3 without an H2)
□ Include secondary keywords and related terms naturally
□ Each heading accurately describes the section beneath it
□ Not used purely for visual styling (no "headings" that are just bold text)
```

### Body Content
```
□ Primary keyword appears in the first 100 words
□ Primary keyword used naturally 2–5 times per 500 words (no counting required)
□ Related terms and semantic vocabulary used throughout
□ Content is unique — not duplicated from other pages on the site
□ Content provides genuine value — not just keyword-filled filler
□ No keyword stuffing (mechanical repetition of the phrase)
□ At least one use of <strong> on a key keyword instance (optional but positive)
□ Long-tail coverage — body text addresses the topic in enough depth to capture related phrases
□ Content length appropriate to complexity — comprehensive, not padded
```

### Images
```
□ All meaningful images have alt attributes
□ Alt attributes use double quotes when text contains spaces
□ Alt text describes the image — not keyword-stuffed
□ Image filenames are descriptive and keyword-relevant
□ Hyphens used as word separators in filenames (not underscores)
□ Images placed in main body content (not in sidebar/nav/footer for primary content)
□ Captions added to key images where helpful
□ No content images blocked in robots.txt
□ Image links use keyword-relevant alt text as anchor text
```

### URL
```
□ Contains the primary keyword
□ All lowercase
□ Hyphens as word separators
□ No query strings in canonical URL
□ No session IDs
□ No unnecessary folder levels
□ Short and descriptive
□ Consistent with URL format for this section of the site
```

### Internal Linking
```
□ Page is linked to from other relevant pages on the site
□ Anchor text on links pointing to this page contains the target keyword
□ Page itself links to related pages using descriptive anchor text
□ No cannibalization — no other pages using the same target keyword in their anchor text to a different page
□ Breadcrumb navigation present and accurate (for deep pages)
```

### Cannibalization Check
```
□ No other page on the site has the same or very similar title tag
□ No other page targets the same primary keyword
□ If multiple pages are related, they link to each other with appropriate hierarchy
```

---

## Site-Wide On-Page Audit Checklist

Use this for auditing an entire site or a section.

### Title Tags (site-wide)
```
□ Run a full site crawl and export all title tags
□ No duplicate title tags
□ No missing title tags (blank or default CMS values like "Untitled" or "Home")
□ All titles under 65 characters
□ No titles that begin with the brand name across every page (except homepage)
□ Consistent formula within each page type (products, categories, blog posts)
□ No generic titles ("Products", "Services", "Page 1")
```

### Meta Descriptions (site-wide)
```
□ No duplicate meta descriptions
□ All high-priority pages have custom meta descriptions
□ Long-tail content pages either have custom descriptions or have the field blank
□ No meta descriptions over 155 characters
```

### H1 Tags (site-wide)
```
□ Every page has exactly one H1
□ No pages with missing H1
□ No pages with multiple H1s
□ H1s are not the same as breadcrumb category labels or site navigation elements
□ CMS-generated H1s are not all identical (e.g., site name repeated as H1)
```

### Content Thin Content Flags (site-wide)
```
□ Identify pages with fewer than 300 words of body content
□ Identify pages with duplicate or near-duplicate body content
□ Identify pages using template content with only proper nouns changed
□ Identify product/category pages with no editorial description (only grid of links)
□ Plan: expand, consolidate, or noindex thin pages
```

### URLs (site-wide)
```
□ No dynamic query strings in indexed URLs (except where unavoidable)
□ No session IDs in indexed URLs
□ No uppercase letters in URL paths
□ No unnecessary tracking parameters in canonical URLs
□ URL structure is flat (no unnecessary depth)
□ Old/changed URLs have 301 redirects in place
```

### Images (site-wide)
```
□ Crawl identifies all images missing alt attributes
□ No images using alt="" on content images (only on decorative images)
□ Image filenames are descriptive (not IMG_0001.jpg across the site)
□ Image directories not blocked in robots.txt
```

---

## On-Page SEO Priority Matrix

When resources are limited, prioritize fixes in this order:

| Priority | Issue | Reason |
|---|---|---|
| **Critical** | Missing or wrong title tag on key pages | Highest-impact ranking element |
| **Critical** | Primary keyword absent from title AND H1 | Page almost certainly won't rank for the term |
| **Critical** | Keyword cannibalization between high-traffic pages | Pages actively competing with each other |
| **High** | Duplicate title tags | Splits the signal; confuses engine about which page is canonical |
| **High** | Missing H1 on key pages | Second-most important on-page element missing |
| **High** | Thin content on pages with external links | Wasted link equity; pages won't convert links to rankings |
| **Medium** | Meta descriptions missing on high-traffic pages | CTR loss in SERPs |
| **Medium** | Images missing alt attributes | Missed image search + relevance reinforcement |
| **Medium** | Poor URL structure (dynamic, dated, or parameter-heavy) | Long-term maintenance and crawl issues |
| **Low** | Suboptimal keyword density in body | Marginal ranking factor if title/H1 are correct |
| **Low** | No bold/strong on key keyword instances | Very small signal; only worth doing after higher priorities |

---

## Quick Reference: Optimal Element Lengths

| Element | Optimal length | Hard limit | Notes |
|---|---|---|---|
| Title tag | 50–65 characters | 65 characters | Google sometimes shows up to 70 |
| Meta description | 150–155 characters | 160 characters | Yahoo! shows up to 165; Bing up to 200+ |
| H1 | 20–70 characters | No hard limit | Should be a clear, readable phrase |
| URL slug | 3–5 words | No hard limit | Shorter is better; keyword + context |
| Alt attribute | 5–15 words | No hard limit | Descriptive phrase, not a sentence |
| Image filename | 2–5 words | No hard limit | `primary-keyword-description.jpg` |
| Domain name | Under 15 characters | No hard limit | Shorter is consistently better |
