# Hreflang Implementation Guide

hreflang is the technical signal that tells Google (and Yandex) which version of a page to show to which user based on language and country. It does not affect Bing, which uses a different system (content-language HTTP header + ccTLD signals).

---

## Language and country codes

**Language codes** follow ISO 639-1 (2-letter codes):
- `en` English
- `de` German
- `fr` French
- `es` Spanish
- `pt` Portuguese
- `ja` Japanese
- `zh` Chinese (use `zh-hans` for Simplified, `zh-hant` for Traditional)
- `ko` Korean
- `ar` Arabic
- `it` Italian
- `nl` Dutch
- `sv` Swedish
- `pl` Polish
- `ru` Russian (note: Yandex also reads hreflang)
- `id` Indonesian
- `th` Thai

**Country codes** follow ISO 3166-1 alpha-2:
- `us` United States
- `gb` United Kingdom
- `de` Germany
- `fr` France
- `es` Spain
- `mx` Mexico
- `br` Brazil
- `au` Australia
- `ca` Canada
- `jp` Japan
- `cn` China
- `in` India
- `sg` Singapore
- `id` Indonesia

**Common combined codes:**
- `en-us` — English, United States
- `en-gb` — English, United Kingdom
- `en-au` — English, Australia
- `en-ca` — English, Canada
- `de-de` — German, Germany
- `de-at` — German, Austria
- `de-ch` — German, Switzerland
- `fr-fr` — French, France
- `fr-ca` — French, Canada
- `fr-be` — French, Belgium
- `es-es` — Spanish, Spain
- `es-mx` — Spanish, Mexico
- `es-ar` — Spanish, Argentina
- `pt-br` — Portuguese, Brazil
- `pt-pt` — Portuguese, Portugal
- `zh-hans-cn` — Simplified Chinese, China
- `zh-hant-tw` — Traditional Chinese, Taiwan

---

## Implementation method 1: HTML `<head>` tags

Place these in the `<head>` section of every page in the international set. Each page must reference ALL other versions, including itself.

**Example: English (US) page with German and French equivalents**

On the English (US) page:
```html
<head>
  <link rel="alternate" hreflang="en-us" href="https://example.com/about/" />
  <link rel="alternate" hreflang="de-de" href="https://example.com/de/ueber-uns/" />
  <link rel="alternate" hreflang="fr-fr" href="https://example.com/fr/a-propos/" />
  <link rel="alternate" hreflang="x-default" href="https://example.com/about/" />
</head>
```

On the German (DE) page — MUST include all the same links:
```html
<head>
  <link rel="alternate" hreflang="en-us" href="https://example.com/about/" />
  <link rel="alternate" hreflang="de-de" href="https://example.com/de/ueber-uns/" />
  <link rel="alternate" hreflang="fr-fr" href="https://example.com/fr/a-propos/" />
  <link rel="alternate" hreflang="x-default" href="https://example.com/about/" />
</head>
```

On the French (FR) page — same again:
```html
<head>
  <link rel="alternate" hreflang="en-us" href="https://example.com/about/" />
  <link rel="alternate" hreflang="de-de" href="https://example.com/de/ueber-uns/" />
  <link rel="alternate" hreflang="fr-fr" href="https://example.com/fr/a-propos/" />
  <link rel="alternate" hreflang="x-default" href="https://example.com/about/" />
</head>
```

---

## Implementation method 2: XML Sitemap

Better for large sites where adding HTML tags to every page is impractical.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9"
        xmlns:xhtml="http://www.w3.org/1999/xhtml">

  <url>
    <loc>https://example.com/about/</loc>
    <xhtml:link rel="alternate" hreflang="en-us" href="https://example.com/about/"/>
    <xhtml:link rel="alternate" hreflang="de-de" href="https://example.com/de/ueber-uns/"/>
    <xhtml:link rel="alternate" hreflang="fr-fr" href="https://example.com/fr/a-propos/"/>
    <xhtml:link rel="alternate" hreflang="x-default" href="https://example.com/about/"/>
  </url>

  <url>
    <loc>https://example.com/de/ueber-uns/</loc>
    <xhtml:link rel="alternate" hreflang="en-us" href="https://example.com/about/"/>
    <xhtml:link rel="alternate" hreflang="de-de" href="https://example.com/de/ueber-uns/"/>
    <xhtml:link rel="alternate" hreflang="fr-fr" href="https://example.com/fr/a-propos/"/>
    <xhtml:link rel="alternate" hreflang="x-default" href="https://example.com/about/"/>
  </url>

  <url>
    <loc>https://example.com/fr/a-propos/</loc>
    <xhtml:link rel="alternate" hreflang="en-us" href="https://example.com/about/"/>
    <xhtml:link rel="alternate" hreflang="de-de" href="https://example.com/de/ueber-uns/"/>
    <xhtml:link rel="alternate" hreflang="fr-fr" href="https://example.com/fr/a-propos/"/>
    <xhtml:link rel="alternate" hreflang="x-default" href="https://example.com/about/"/>
  </url>

</urlset>
```

---

## Implementation method 3: HTTP headers

Use for non-HTML content (PDFs, etc.) or when you cannot modify the page `<head>`:

```
Link: <https://example.com/about/>; rel="alternate"; hreflang="en-us",
      <https://example.com/de/ueber-uns/>; rel="alternate"; hreflang="de-de",
      <https://example.com/fr/a-propos/>; rel="alternate"; hreflang="fr-fr"
```

---

## Understanding `x-default`

`x-default` tells Google which page to show when no hreflang tag matches the user's language/country. It's the fallback.

Common uses:
- Point to your homepage or default language page
- Point to a language selector page if you have one
- Point to your English (international) version if you have no US-specific version

```html
<link rel="alternate" hreflang="x-default" href="https://example.com/" />
```

---

## Hreflang audit checklist

Run this audit on your site before going live and quarterly after:

**Coverage:**
- [ ] Every international page has hreflang tags
- [ ] Every page references itself (self-referencing tag present)
- [ ] Every page references ALL other language/country equivalents
- [ ] `x-default` is present on all pages

**URL integrity:**
- [ ] All hreflang URLs are absolute (start with https://)
- [ ] All hreflang URLs return 200 status (not 301/404)
- [ ] All hreflang URLs match canonical URLs exactly (no trailing slash inconsistency)
- [ ] No redirected URLs used in hreflang

**Language/country codes:**
- [ ] All codes follow ISO 639-1 + ISO 3166-1 format
- [ ] No invented codes (there is no `hreflang="latam"` or `hreflang="global"`)
- [ ] Country codes used where country-specific targeting is intended

**GSC verification:**
- [ ] Check GSC International Targeting report for hreflang errors
- [ ] Confirm correct language versions appearing in correct country SERPs
- [ ] No "missing return tags" errors in GSC

---

## Common errors and fixes

| Error | Cause | Fix |
|---|---|---|
| "Missing return tag" in GSC | Page A references Page B but Page B doesn't reference Page A | Add the missing tag to Page B |
| English version ranking in Germany | hreflang not present or ignored | Check for URL mismatches, add missing tags |
| hreflang on non-canonical URLs | Tags pointing to redirected URLs | Update all tags to point to canonical URL |
| Only home page has hreflang | Partial implementation | Roll out to all pages, not just home page |
| Using `hreflang="en"` for all English | No country differentiation | Use `en-us`, `en-gb`, `en-au` as appropriate |
