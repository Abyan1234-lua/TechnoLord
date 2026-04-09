# Video SEO Reference

*Sourced from: The Art of SEO — Enge, Spencer, Fishkin & Stricchiola (Ch. 8: Optimizing for Vertical Search)*

---

## Video SEO Strategy Overview

Video search optimization works across three parallel scenarios. Run all three for maximum coverage.

```
Scenario 1: Videos hosted on YOUR site
  → Crawled by video search engines (Truveo, Google)
  → Optimization: on-page content, Video Sitemap, raw file links

Scenario 2: RSS / MRSS feed submission
  → Submitted to Yahoo! Video, Blinkx, and similar
  → Optimization: title, description, keywords, thumbnail, full transcript

Scenario 3: Upload to video platforms
  → YouTube, Vimeo, Dailymotion, Metacafe, etc.
  → Optimization: platform-specific metadata, engagement, distribution
```

---

## YouTube Upload Checklist

### Pre-upload

```
□ Video filename contains target keyword (e.g., how-to-make-sourdough-bread.mp4)
□ File size under 100 MB (compatible with all major platforms)
□ Video length ideally under 5 minutes (unless subject genuinely requires more)
□ Content is genuinely useful, entertaining, or informative
□ Branding or watermark included for commercial content
□ Script written with keyword-rich language for future voice-recognition indexing
```

### Title (most important field)

```
□ Primary keyword appears near the start of the title
□ Title is under 62 characters (YouTube's display limit)
□ Title is catchy and click-worthy (drives views → drives ranking)
□ Include "video" naturally in the title where it fits
□ Avoid stop words (the, and, of) at the start

✓ "Sourdough Bread for Beginners — Full Video Tutorial"
✗ "How I Made Some Bread the Other Day"
```

### Description

```
□ Full URL to your site in the first line (must include http:// to be clickable)
□ Primary keyword in first sentence of description
□ Full keyword-rich description of the video content (2–5 paragraphs)
□ Link to related content/page on your site
□ Secondary keywords used naturally throughout
□ Call to action included (subscribe, visit site, comment)
```

### Tags

```
□ All available tag space used
□ Tags include: primary keyword, secondary keywords, category descriptors
□ Adjective tags included (describes mood/style: "beginner", "quick", "detailed")
□ Tags match the title and description for top keywords
□ Tags diversified across your video library (don't use identical tags on every video)
□ Natural language phrases avoided in tags (single words and short phrases work best)
□ Filler words (and, the, of) NOT used in tags — they waste tag character space
```

### Thumbnail

```
□ Custom thumbnail set (if platform allows)
□ Subject clearly identifiable at small (thumbnail) size
□ High contrast — not dark or muddy
□ Compelling image that represents the video well
□ Face visible if it's a person (face thumbnails typically get higher CTR)
□ Thumbnail different per video in your library (not generic)
```

### Engagement settings

```
□ Ratings enabled (search engines weight user ratings)
□ Comments enabled (engagement signals)
□ Video replies enabled (where available)
□ Embedding enabled (embeds spread the video and create indirect links)
□ "Send to a friend" or sharing options enabled
□ End-screen or cards added with call-to-action and link to related content
```

---

## Platform Distribution Reference

| Platform | Max length | Max size | Notes |
|---|---|---|---|
| YouTube | 15 min (unverified) / longer (verified) | 128 GB | Largest audience; Google Universal Search integration |
| Vimeo | Varies by plan | Varies by plan | Higher-quality audience; less spam |
| Dailymotion | 60 min | 2 GB | Good secondary distribution |
| Metacafe | 20 min | 100 MB | Niche but indexed by Google |
| Flickr | 90 seconds | 500 MB (video) | Very short clips only |
| Yahoo! Video | Varies | Varies | Also accepts MRSS feed |

**TubeMogul:** Upload once, distribute to multiple platforms simultaneously, get unified analytics. Worth using for any consistent video publishing program.

---

## Video Sitemap Reference

A Video Sitemap is a specialized XML file submitted to Google Search Console that tells Google about video content on your site. It dramatically improves discovery and indexation of hosted videos.

### When to use it
- You host videos directly on your own site (not just embedded YouTube)
- You want Google to index your video content as quickly as possible
- Your videos are not being discovered through normal web crawling

### Key tags in a Video Sitemap

```xml
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9"
        xmlns:video="http://www.google.com/schemas/sitemap-video/1.1">
  <url>
    <loc>http://www.example.com/videos/how-to-make-sourdough/</loc>
    <video:video>
      <video:thumbnail_loc>
        http://www.example.com/images/sourdough-thumbnail.jpg
      </video:thumbnail_loc>
      <video:title>Sourdough Bread for Beginners</video:title>
      <video:description>
        A complete guide to making your first sourdough loaf from starter to finish.
      </video:description>
      <video:content_loc>
        http://www.example.com/videos/sourdough-beginners.mp4
      </video:content_loc>
      <video:duration>300</video:duration>
      <video:publication_date>2024-03-19</video:publication_date>
    </video:video>
  </url>
</urlset>
```

Submit via Google Search Console → Sitemaps.

---

## MRSS Feed Template

For submitting to Yahoo! Video, Blinkx, and other feed-based video search engines:

```xml
<rss version="2.0" xmlns:media="http://search.yahoo.com/mrss/">
  <channel>
    <title>Your Channel Name</title>
    <link>http://www.yourdomain.com</link>
    <description>Your channel description</description>
    <item>
      <title>Sourdough Bread for Beginners</title>
      <link>http://www.yourdomain.com/videos/sourdough-beginners/</link>
      <description>A complete beginner's guide to sourdough bread baking.</description>
      <media:content url="http://www.yourdomain.com/videos/sourdough.mp4"
                     type="video/mp4"
                     duration="300"/>
      <media:thumbnail url="http://www.yourdomain.com/images/sourdough-thumb.jpg"/>
      <media:keywords>sourdough, bread, baking, beginner, tutorial, video</media:keywords>
      <media:text type="plain">
        [Full transcript of the video goes here. This is the most valuable field for
        video search engines — it turns an opaque video into a fully indexable document.]
      </media:text>
      <media:category>Food &amp; Cooking</media:category>
    </item>
  </channel>
</rss>
```

**Transcript note:** The `<media:text>` field (full transcript) is the highest-value optimization you can make for MRSS-based video search engines. Write or generate a transcript for every video.

---

## Video SEO — The Link-Building Problem and Solution

**The problem:** Most links generated when a YouTube video goes viral point to `youtube.com/watch?v=...`, not to your site. Your domain captures the brand exposure but not the link equity.

**Solutions:**

| Approach | Link equity benefit |
|---|---|
| Create an on-site landing page featuring the video + unique additional content | Links to your landing page go to your domain directly |
| Include clickable URL in YouTube description | Drives traffic; no link equity (YouTube links are nofollow) |
| Use the video to build relationships with bloggers/media who then write about it and link to your site | High-quality editorial links to your domain |
| Host a version of the video on your own site alongside YouTube embed | Allows a Video Sitemap; some crawlers will link to your hosted version |

**Best practice:** Always pair a YouTube video with a dedicated on-site page that adds something the video alone doesn't provide — a transcript, detailed show notes, related resources, or a downloadable asset. This gives external linkers a reason to link to your domain, not just the YouTube page.
