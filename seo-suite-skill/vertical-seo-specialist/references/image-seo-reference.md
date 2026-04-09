# Image SEO Reference

*Sourced from: The Art of SEO — Enge, Spencer, Fishkin & Stricchiola (Ch. 8: Optimizing for Vertical Search)*

---

## Image Optimization Technical Checklist

### Filename

```
□ Filename contains the primary keyword
□ Words separated by hyphens (not underscores, not spaces)
□ Descriptive of actual image content
□ Lowercase (avoids case-sensitivity issues on Linux servers)

✓ golden-gate-bridge-sunset.jpg
✗ IMG_4728.jpg
✗ golden_gate_bridge.jpg
✗ GoldenGateBridge.jpg
```

### Alt Attribute

```
□ Every image has an alt attribute
□ Alt text is enclosed in double quotes (required when text contains spaces)
□ Alt text describes the image for someone who cannot see it
□ Alt text contains the primary keyword naturally (not stuffed)
□ Alt text is not empty: alt="" is only correct for purely decorative images

✓ <img alt="Golden Gate Bridge at sunset" src="golden-gate-bridge-sunset.jpg">
✗ <img src="golden-gate-bridge-sunset.jpg">  (missing alt)
✗ <img alt=Golden Gate Bridge src="...">  (missing quotes — drops all words after first)
✗ <img alt="golden gate bridge sunset photo image picture" src="...">  (keyword stuffed)
```

### URL / SRC

```
□ Image URL is clean — no excessive query string parameters
□ If query strings unavoidable, limited to 2–3 parameters
□ Image directory is NOT blocked in robots.txt
□ Images are accessible when called from external domains (hot-linking enabled)
□ Keyword present in the URL path where possible:
   ✓ /images/golden-gate-bridge/sunset.jpg
   ✗ /img.php?id=4728&type=jpg&quality=high&thumb=0
```

### Page-Level Context

```
□ Page title, H1 heading, and body content all reinforce the image subject
□ Descriptive caption placed directly below each key image
□ Relevant text appears immediately before and immediately after the image
□ Images NOT stored inside: sidebar columns, header elements, footer nav
   (Engines treat these as site decor and downrank or ignore them)
```

### Image Quality

```
□ Image reads clearly at thumbnail size (high contrast, clear subject)
□ Embedded thumbnail saving DISABLED in Photoshop and editors
   (Embedded thumbnails bloat file size and can conflict with engine-generated thumbnails)
□ For Google Product Search: use square images (fits 90×90px thumbnail best)
□ Product images: subject fills the frame, high contrast against clean background
```

### Duplicate Image Handling

If using licensed images, manufacturer photos, or images that also appear on other sites:

```
□ Modify the image file before uploading:
   — Resize (change pixel dimensions)
   — Adjust compression level
   — Trim a few pixels from height or width (changes aspect ratio)
   — Resave (new file metadata, new file size)
□ These changes ensure your file passes image duplicate content filters
□ Add a watermark with your site URL on images likely to be redistributed
□ Verify you have legal rights to all images displayed on your site
```

### Robots.txt / Server Configuration

```
□ /images/ directory (and any other image directories) NOT blocked in robots.txt
□ Server allows hot-linking of images from other domains
   (Required for images to appear in search engine results pages)
□ Image CDN domains are accessible to crawlers (if using a CDN for images)
```

---

## Image Context Signal Hierarchy

Search engines build confidence in an image's subject by cross-referencing multiple signals. The more signals that align, the stronger the ranking.

```
Highest weight:
├── Page title tag
├── H1 heading tag
├── Alt attribute text
├── Image filename
│
Medium weight:
├── Caption text (directly below image)
├── Text immediately before the image
├── Text immediately after the image
├── Surrounding paragraph text
│
Lower weight:
├── Page body content (further from image)
├── Meta description
├── URL path
└── Inbound links to the page
```

**Consistency rule:** All signals should reinforce the same topic. A page about the Golden Gate Bridge with an image called `photo1.jpg` with no alt text will lose to a page where every signal says "Golden Gate Bridge."

---

## Flickr Optimization Workflow

### Upload checklist (per photo)

```
□ Descriptive title added (keyword-rich)
□ Tags added — as many accurate keywords as possible
   — Wrap multi-word tags in quotes: "pickup truck", "golden gate bridge"
□ Description written — includes context about the photo
□ Link to your website added in Description field (use contextual anchor text)
□ Photo set to Public visibility (not "Friends and Family only")
□ Geotagged if location-specific
□ Creative Commons license applied (if you want it to be reusable)
□ Note added on photo if humorous or interactive (encourages engagement)
```

### Ongoing organization

```
□ Thematic Sets created (group related photos)
□ Each photo added to all relevant Sets
□ Relevant Flickr Groups identified by searching your keywords in Flickr
□ Photos submitted to relevant Groups (aim for Groups with large member counts)
□ Total photo volume growing — more photos = more cumulative authority and more
  chances for individual photos to rank
```

### Why Flickr works for SEO

- Flickr has high domain authority — its pages can rank in general web search results
- A well-optimized Flickr photo page can rank on the same query as your main site — giving you 2+ positions on the same SERP
- In some cases, the Flickr result outranks the main site page (especially for image-heavy queries)
- Flickr links back to your site (nofollow, but drives direct traffic and brand awareness)
- Flickr tags create a structured folksonomy that both users and crawlers navigate

---

## Image Search Strategy by Industry

| Industry | Image search priority | Primary tactic |
|---|---|---|
| E-commerce | Very high | Product image optimization; every product image correctly named, alt-tagged, and captioned |
| Travel / hospitality | Very high | Location/property photos in Flickr; Universal Search shows travel images prominently |
| Food / restaurant | High | Dish photos, location photos; tie to local search |
| Architecture / design | High | Portfolio images with descriptive filenames; Flickr sets by project |
| Fashion | High | Product images; optimize for both web and image search |
| Medical / scientific | Medium | Diagrams, anatomy images; strong alt text and captions critical |
| SaaS / software | Low | Screenshots may appear in image search but rarely drive valuable traffic |
| Professional services | Low | Team photos, office photos — low commercial value from image search |

---

## Universal Search — Why Image SEO Matters Beyond Image Search

Since Google Universal Search (2007), image results appear inline in the main web SERPs for many queries. This means:

- An optimized image on your site can occupy a position on a SERP where you'd never rank with a text result
- Image results often appear above or within the top organic results
- Queries for visual topics (products, places, people, events) frequently trigger image blended results
- You can have both a web listing and an image listing for the same query — doubling your SERP presence

**Strategic implication:** Even sites that don't consider themselves "image sites" should invest in image optimization for their key landing pages. The competition for image slots is dramatically lower than for web search slots.
