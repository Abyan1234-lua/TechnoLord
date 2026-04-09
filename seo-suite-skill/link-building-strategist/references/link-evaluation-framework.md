# Link Evaluation Framework

*Sourced from: The Art of SEO — Enge, Spencer, Fishkin & Stricchiola (Ch. 7: Creating Link-Worthy Content and Link Marketing)*

---

## Individual Link Prospect Scoring

Use this to rank prospective link opportunities before investing outreach time.

### Scoring criteria

| Criterion | Score 1 | Score 2 | Score 3 | Score 4 | Score 5 |
|---|---|---|---|---|---|
| **Domain authority** (Ahrefs DR / Moz DA) | <20 | 20–39 | 40–59 | 60–79 | 80+ |
| **Page authority** (specific linking page) | Very low | Low | Medium | High | Very high |
| **Topical relevance** (site/page to your content) | Unrelated | Loosely related | Related industry | Same niche | Direct topic match |
| **Independence** (no existing business relationship) | Clearly paid/traded | Likely exchanged | Some relationship | Mostly independent | Fully editorial |
| **Outbound links on page** (fewer = more value) | 500+ | 200–499 | 100–199 | 20–99 | <20 |
| **Trust signals** (site is indexed, has own links, real audience) | No signs | Weak | Average | Good | Excellent |

**Total possible score: 30**

**Priority tier:**
- 24–30 → Very high value: pursue with maximum effort and custom content if needed
- 18–23 → High value: pursue with customized outreach
- 12–17 → Medium value: pursue with template-based personalized outreach
- 6–11 → Low value: pursue at scale with minimal time investment
- <6 → Not worth pursuing

---

## Quick Prospect Checklist

Before adding a site to your outreach list:

```
□ Is the domain indexed by Google? (Search: site:domain.com)
□ Does the site have its own inbound links? (Check Ahrefs/Moz)
□ Is the site's content genuinely high-quality and editorial?
□ Is the site topically relevant to your content?
□ Does the specific page you'd be linked from have a chance of being seen?
□ Is the site NOT primarily a directory for webmasters/SEOs?
□ Is there no sign of a link scheme (link farm, PBN, obvious link selling)?
□ Are the other outbound links on the prospective page from quality sites?
```

If any answer is "no" on the first three — skip it.

---

## The Link Value Formula (Simplified)

From the original PageRank model, a rough guide to the value a link passes:

```
Passed value = (Page's total authority) / (Number of outbound links on that page)
```

Practical implication: A link from a page with 5 outbound links passes far more value than a link from a page with 500 outbound links — even if the domain authority is identical.

Check outbound link count using Screaming Frog, browser extension, or source inspection.

---

## Directory Assessment Criteria

Use this checklist to determine if a directory is worth submitting to:

### Green flags (likely to pass value)

- [ ] The fee is for editorial review, not for guaranteed placement
- [ ] Editors can reject submissions (and do)
- [ ] Editors can change the category, title, or description of your listing
- [ ] The listed sites are consistently high quality
- [ ] The directory appears in search engine results for its own name and niche terms
- [ ] The directory is marketed to end users, not to webmasters or SEOs
- [ ] The directory does not offer "premium placement" tiers for higher fees

### Red flags (likely low or zero value — avoid)

- [ ] All paid submissions are automatically accepted
- [ ] The directory is marketed to webmasters, SEOs, or those seeking rankings
- [ ] Premium placements available at higher fee levels
- [ ] Listed sites are low-quality, spam-heavy, or thin
- [ ] The directory's own pages do not rank in search engines
- [ ] The directory promotes itself by citing "SEO value" or "PageRank" for listings

---

## Anchor Text Distribution Guidelines

A natural link profile has varied anchor text. Audit your anchor text mix regularly.

### Healthy anchor text distribution (approximate targets)

| Anchor text type | Example | Target proportion |
|---|---|---|
| Brand name | "Acme Tools" | 30–50% |
| Brand + keyword | "Acme Tools drill bits" | 5–10% |
| Exact keyword match | "drill bits" | 5–10% |
| Partial keyword match | "best bits for drilling" | 10–20% |
| Generic ("click here", "here", "this") | "read more here" | 5–15% |
| Naked URL | "https://acmetools.com/drill-bits" | 10–20% |
| Image link (alt text) | (image) | Variable |

**Warning signs:**
- Exact-match keyword anchor text above ~20% of profile → manipulation flag
- Near-zero brand/URL anchors → artificial profile
- One anchor type dominating 80%+ of profile → unnatural

---

## Link Velocity Monitoring

Track your link acquisition rate monthly. Sudden spikes look manipulative even if the links are white-hat.

| Scenario | Interpretation | Action |
|---|---|---|
| Gradual, consistent growth | Healthy organic profile | Keep current approach |
| Sudden spike after major content or PR | Natural (newsworthy event) | Document the trigger for reference |
| Sudden spike with no content/PR trigger | Potential manipulation signal | Audit source; slow acquisition if paid |
| Steady decline | Attrition from lost links, site changes | Reclaim lost links; review for deindexed linkers |
| Overnight appearance of hundreds of identical-anchor links | Link scheme or attack | Investigate immediately; disavow if spam |

**Useful benchmark:** Check your link acquisition rate in Ahrefs, Majestic, or Moz monthly. Compare against competitors. A large, sudden gap between your rate and competitors may indicate either a problem or an opportunity.

---

## Diagnosing a Weak Link Profile

Use this diagnostic if rankings are stuck despite good on-page SEO:

```
Step 1: Unique linking domains
  → Fewer than competitors for target keywords? → Focus on acquiring new root domains

Step 2: Authority of linking domains  
  → Links mostly from low-authority sites? → Pursue higher-authority targets

Step 3: Topical relevance
  → Links mostly from unrelated industries? → Refocus outreach on niche-relevant sites

Step 4: Anchor text profile
  → Over-concentrated in one anchor type? → Diversify anchor text intentionally

Step 5: Link velocity
  → Recent drop in new link acquisition? → Ramp up content and outreach activity

Step 6: Trust profile
  → Many links from low-trust or flagged domains? → Consider disavow; build more trusted links

Step 7: Deep links vs. homepage links
  → All links going to homepage, none to key landing pages? → Run targeted link-building campaigns to priority pages
```
