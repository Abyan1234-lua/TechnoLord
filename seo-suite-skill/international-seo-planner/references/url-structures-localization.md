# URL Structures and Localization Patterns

---

## URL structure comparison: detailed trade-offs

### ccTLDs — e.g., example.de, example.co.uk

**Geotargeting signal:** Strongest — search engines treat ccTLDs as definitive country indicators
**Link equity:** Separate per domain — starts from zero for each new ccTLD
**Hosting:** Should be hosted in-country for full benefit
**Cost:** High — domain registration fees + separate infrastructure per country
**Setup complexity:** High — each is effectively a separate site
**Maintenance:** High — separate GSC properties, sitemaps, tracking
**User trust:** Highest — local users strongly prefer local TLDs for purchasing

**When it's worth it:**
- Long-term market commitment (3+ years)
- Local operations or team in that country
- E-commerce where local trust signals directly impact conversion
- Budget for proper ongoing maintenance per market

**When to avoid:**
- Startup or exploratory phase — you may abandon the market
- Limited engineering resources
- No local team to maintain the site

---

### Subdomains — e.g., de.example.com, uk.example.com

**Geotargeting signal:** Moderate — must set in Google Search Console, Google sometimes treats as separate site
**Link equity:** Partial transfer from main domain — not as strong as subfolders
**Hosting:** Can be hosted separately per subdomain (this is the main advantage over subfolders)
**Cost:** Moderate — no domain fees, but separate infrastructure
**Setup complexity:** Medium
**Maintenance:** Medium — separate GSC properties and sitemaps recommended

**When it works well:**
- Strong main domain with good authority
- Need local hosting per market (important for speed and geotargeting signals)
- Centralized content team but distributed infrastructure
- Established international brands maintaining existing subdomain structure

**Common pattern:** `de.example.com`, `fr.example.com`, `uk.example.com`

---

### Subfolders — e.g., example.com/de/, example.com/fr/

**Geotargeting signal:** Weakest standalone — must use hreflang + GSC geotargeting settings
**Link equity:** Full — inherits all main domain authority immediately
**Hosting:** Same server as main site (can't be hosted locally per country)
**Cost:** Lowest — no additional infrastructure
**Setup complexity:** Lowest
**Maintenance:** Simplest — single GSC account, single sitemap with hreflang annotations

**When it's the right choice:**
- Most companies, most situations
- Starting international SEO for the first time
- Strong existing domain that you don't want to dilute
- Limited budget or team
- Markets where you're exploring before committing

**Common pattern:** `example.com/de/`, `example.com/fr/`, `example.com/es-mx/`

---

## Handling multiple countries with the same language

This is one of the trickiest scenarios. You have the same language (e.g., Spanish) but different target countries (Mexico, Argentina, Spain). Three options:

**Option A: Language-only targeting (not recommended for most)**
Use `hreflang="es"` with no country. Google serves the same page to all Spanish speakers. Works if your content genuinely applies to all Spanish-speaking countries.

**Option B: Country-specific subfolders per market**
```
example.com/es-mx/   (Spanish, Mexico)
example.com/es-ar/   (Spanish, Argentina)
example.com/es-es/   (Spanish, Spain)
```
Each gets hreflang with country code. Requires unique content per country (at minimum, localized examples, pricing, CTAs).

**Option C: Country-specific content with shared base**
Same as B, but start with one country, add others as you validate demand. Avoids over-investing in thin content for multiple markets simultaneously.

**Rule of thumb:** If content, pricing, legal requirements, or cultural references differ meaningfully between countries, separate them. If they don't, language-only targeting is acceptable.

---

## Localization depth guide

### What to localize at each tier

**Tier 1 — Full localization (flagship markets)**

Every element is native:
- Copy written by native speakers from the target country, not translated
- Local examples, case studies, and customer logos
- Pricing in local currency with local tax handling
- Local customer support contact information
- Local social media presence linked from the site
- Local payment methods
- Date/time in local format
- Local phone number format
- Units of measure (metric vs. imperial where relevant)
- Legal copy relevant to local law (GDPR for EU, LGPD for Brazil, etc.)

**Tier 2 — Adapted localization (growth markets)**

Professional translation with human review, plus:
- Local currency and pricing
- Local CTAs adapted for market expectations
- At least one local case study or customer reference
- Local contact information or timezone-appropriate support
- Legal compliance elements

**Tier 3 — Minimal localization (exploratory markets)**

Professional translation, native review pass:
- Translated copy with accent/spelling corrections
- Currency conversion shown (may not be true local pricing)
- Global CTAs (not locally adapted)
- Acceptable as a test; not sustainable long-term

---

## Common localization mistakes by region

**Europe (EU):**
- Forgetting GDPR cookie consent for all EU countries — required before deploying
- Using US-style "Get started for free" aggressive CTAs — European users often prefer softer, more formal language
- Using USD pricing — show EUR, GBP, CHF etc. and show VAT-inclusive pricing

**Latin America:**
- Treating all Spanish-speaking countries as one market
- Using Spain Spanish for Mexico (notable vocabulary and tone differences)
- Not accounting for Brazil as Portuguese-speaking — never target Brazil with Spanish content
- Missing local payment methods (Mercado Pago, OXXO, Boleto Bancário are critical for conversion)

**APAC:**
- Treating APAC as a single region — it's more diverse than any other
- Using Simplified Chinese (Mainland China) content for Taiwan or Hong Kong (where Traditional Chinese is expected)
- Underestimating the impact of local search engines in China (Baidu) and Japan (Yahoo Japan still significant)
- Missing WeChat integration for China-targeted content

**Middle East / Arabic:**
- Forgetting right-to-left (RTL) text direction requires engineering work
- Machine-translating Arabic — Arabic language quality is very sensitive to users
- Not adapting visuals — imagery standards differ significantly

**Germany specifically:**
- German users are among the most skeptical of aggressive marketing online — trust signals matter more here than almost anywhere
- Data privacy concerns are acute — be transparent about data use
- "Impressum" (legal notice page) is legally required for German-targeted commercial sites
