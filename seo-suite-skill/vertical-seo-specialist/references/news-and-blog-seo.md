# News, Blog & RSS SEO Reference

*Sourced from: The Art of SEO — Enge, Spencer, Fishkin & Stricchiola (Ch. 8: Optimizing for Vertical Search)*

---

## News Search — Submission & Requirements

### Submission URLs

| Engine | Submission URL |
|---|---|
| Google News | google.com/support/news_pub/bin/request.py |
| Yahoo! News | help.yahoo.com/l/us/yahoo/news/forms/submitsource.html |

### Google News minimum requirements

**Content requirements:**
- Minimum ~10 new articles per week (consistent volume — evaluated as a source, not individual articles)
- Content must be genuine news or feature stories — not marketing copy, product pages, or company announcements
- Articles follow traditional news structure: keyword-rich headline + strong opening paragraph that leads with the main point + descending-importance body + summary conclusion
- Named authors/editors required — provide a 2–3 sentence bio for each (minimum 3 named authors)
- Include a history of the site and traffic statistics in your submission

**Technical requirements:**
- All articles at **static, permanent URLs** — URL and content must not change after publication
- URLs accessible via **standard HTML text links** (not JavaScript-rendered URLs)
- Content in **standard HTML only** — no PDFs, no Flash, no frames
- **UTF-8 character encoding**
- Create and submit a **Google News Sitemap** via Google Search Console

**Google News Sitemap:**
The News Sitemap format differs from a standard XML sitemap. It can be implemented as an RSS or Atom feed. Submitting it speeds up article discovery significantly. Even after acceptance, a News Sitemap is best practice for all new stories.

### Yahoo! News requirements

- Submit an **RSS feed** (standard RSS format accepted)
- Content bar is higher than Google News — Yahoo! requires significant quantities of unique, high-value content not available from other sources
- If you meet Google News standards, Yahoo! News submission requirements are technically satisfied

---

## RSS Feed Optimization Checklist

### Feed structure

```
□ Full article text in feed (not truncated summaries)
□ Multiple feeds available: by category, by content type, by author (where applicable)
□ Media enclosures included for audio/video content (enables podcast directories)
□ Feed URL is on YOUR domain — not a third-party provider URL
□ <link rel="alternate" type="application/rss+xml"> autodiscovery tag in <head> of all pages
□ One-click subscription buttons present: My Yahoo!, Bloglines, Google Reader, etc.
```

### RSS tracking setup

**Open rate tracking (web bug):**
```xml
<!-- Add inside <content:encoded> container -->
<img src="http://www.yourdomain.com/track/[unique-id]" border="0" height="1" width="1">
```

**Click-through tracking:**
Replace all `<link>` URLs with tracked redirect URLs:
```
http://www.yourdomain.com/rss.php?[unique-tracking-id]
```
Then 301-redirect from the tracked URL to the final canonical URL.

**Critical:** If using FeedBurner or SimpleFeed, configure click-tracked redirects to use **301** (not the default 302). 302 redirects do not pass link juice from syndicated sites.

**Subscriber tracking:**
Use FeedBurner to identify subscriber counts. Aggregator user agents (e.g., `Bloglines/2.0 (…; xx subscribers)`) reveal subscriber counts in server logs. Bots and direct browser requests don't count.

### Feed pinging

**Pingomatic.com** — pings all major feed services simultaneously. Use on every new post.

**Yahoo! direct ping:**
```
http://api.my.yahoo.com/rss/ping?u=http://www.yourdomain.com/rss
```
(Replace with your actual feed URL)

**Additional pinging resources:**
- Google Blog Search ping: via Google Webmaster Tools
- Feedburner (if used): configure auto-ping on new posts

### Protecting feed content

Monitor server logs for referrers syndicating your feed without passing link credit:
- Look for sites stripping `href` from your links
- Look for sites applying `rel="nofollow"` to your links
- Block offending IP addresses from accessing your feed

---

## Blog SEO Checklist

### Technical setup

```
□ Title tags — custom, keyword-rich per post (not CMS-default)
□ URLs — keyword-bearing, hyphen-separated, no dates in URL
   ✓ /blog/how-to-optimize-images-for-search
   ✗ /blog/2024/03/19/post-1234
□ 301 redirect: non-www → www (or vice versa) for ALL pages (not just homepage)
□ 301 redirects in place for any platform migration (old URL → new URL, per post)
□ Category names are keyword-rich (appear in category page title tags)
□ Sticky posts configured for category pages (adds keyword intro copy to category pages)
```

### Internal linking

```
□ Post title is a clickable link to the permalink (not just "Permalink" text)
□ New posts link internally to older relevant posts using keyword-rich anchor text
□ Related Posts plugin installed and configured
□ Top posts linked from multiple places with descriptive anchor text
□ Tag cloud implemented (keyword-rich navigation for users and crawlers)
□ Author profile pages created for each contributing author
□ Per-author RSS feeds offered
```

### Content standards

```
□ Bold/strong and em tags used deliberately within post body (mild relevance signal)
□ rel="nofollow" applied to all comment links and trackback links
□ External links in posts — use nofollow where you don't editorially vouch for the site
□ Inbound link anchor text audit done — weak anchors identified for revision requests
```

---

## News Article Structure Template

Use this structure for every news/feature story targeting news search:

```
HEADLINE
[Keyword-rich, catchy, under 70 characters ideally]
[Primary keyword near the start of the headline]

OPENING PARAGRAPH
[Lead with the most important information — who, what, when, where, why]
[Include the primary keyword naturally in the first sentence]
[This paragraph determines whether the reader continues — make it compelling]

BODY PARAGRAPHS
[Descending order of importance]
[Each paragraph covers one point]
[Include supporting data, quotes, and evidence]
[Use subheadings (H2/H3) for longer pieces to aid scannability]

CONCLUDING PARAGRAPH
[Summary of key points]
[Call to action or forward-looking statement where appropriate]

BYLINE
[Author name — required for news search credibility]
[Author bio linked or included]

METADATA
Title tag: [Headline] | [Site Name]
Meta description: [First 1–2 sentences of the opening paragraph]
URL: /news/[keyword-rich-slug]/
```

---

## Blog Platform SEO Comparison

| Feature | WordPress (self-hosted) | Blogger | Squarespace | Medium |
|---|---|---|---|---|
| Custom title tags | ✓ (with plugin) | Limited | ✓ | ✗ |
| Custom URL slugs | ✓ | Limited | ✓ | ✗ |
| Remove dates from URLs | ✓ | Limited | ✓ | ✗ |
| Full canonical control | ✓ | Limited | ✓ | Limited |
| 301 redirect management | ✓ | Limited | ✓ | ✗ |
| RSS feed ownership | ✓ | Google-controlled | ✓ | Medium-controlled |
| Plugin ecosystem for SEO | Extensive (Yoast, RankMath) | None | Limited | None |
| Schema markup | ✓ (via plugin) | Limited | Limited | ✗ |

**Recommendation:** Self-hosted WordPress is the default choice for any serious SEO blog. Full control over every technical element.

**WordPress SEO essentials:**
- Yoast SEO or RankMath (title tag, meta description, canonical, XML sitemap, schema)
- SEO Title Tag plugin (custom title tag per post override if needed)
- WordPress Slug Trimmer or Automated SEO Friendly URL (trim long slugs)
- Yet Another Related Posts Plugin (internal linking automation)
- A caching plugin (WP Super Cache, W3 Total Cache) — page speed affects crawl rate
