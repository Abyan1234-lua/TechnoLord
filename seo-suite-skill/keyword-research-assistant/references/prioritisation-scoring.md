# Keyword Prioritisation Scoring

Prioritising keywords prevents the most common keyword research failure: producing an enormous list that results in no action because nobody knows where to start.

A good prioritisation model answers: *"If we could only publish 10 pages in the next 90 days, which 10 keywords should they be built around?"*

---

## The prioritisation framework

### Four scoring dimensions

Every keyword is scored on four dimensions. Scores combine to produce a final priority score used for ranking the list.

---

### Dimension 1: Business relevance (1–3)

How directly does traffic from this keyword connect to your business goal?

| Score | Meaning | Examples |
|---|---|---|
| **3** | Direct path to conversion | "[product] pricing", "[tool] free trial", "buy [category]", "[brand] vs [competitor]" |
| **2** | Target audience present, indirect conversion | "how to [problem your product solves]", "best practices for [relevant topic]" |
| **1** | Related audience, weak conversion link | "[broad industry] trends", "what is [tangential concept]" |

**Decision rule:** When in doubt, ask "Would the typical user who searches this keyword ever become a customer?" If yes and relatively soon → 3. If possibly, over time → 2. If unlikely → 1.

---

### Dimension 2: Achievability (0–5)

Can this site realistically reach page 1 for this keyword in 6–12 months?

This is a function of keyword difficulty (KD) relative to your domain's current authority level.

| KD score | New site (DA <20) | Growing site (DA 20–40) | Established site (DA 40–60) | High authority (DA 60+) |
|---|---|---|---|---|
| 0–15 | 5 | 5 | 5 | 5 |
| 16–25 | 4 | 5 | 5 | 5 |
| 26–35 | 2 | 4 | 5 | 5 |
| 36–50 | 0 | 2 | 4 | 5 |
| 51–65 | 0 | 1 | 2 | 4 |
| 66–80 | 0 | 0 | 1 | 2 |
| 81–100 | 0 | 0 | 0 | 1 |

**Note on DA:** Domain Authority (Moz), Domain Rating (Ahrefs), or Authority Score (Semrush) all differ. Use whichever tool you have and calibrate against actual rankings. The table above is a guide, not a formula — use judgement.

**Shortcuts:**
- If no tool access: search the keyword and assess whether current top 10 results are from sites with similar authority to yours. If 3+ results are from blogs or smaller sites, it's likely achievable.
- Fresh content on a new domain rarely ranks for KD > 25 without links. If the site has no backlinks, be conservative.

---

### Dimension 3: Intent match (1–3)

How precisely does the keyword's intent match the page type you're planning to build?

| Score | Meaning |
|---|---|
| **3** | Exact match — the keyword intent perfectly fits the planned page type |
| **2** | Strong match — the intent is close; the page would satisfy most searchers |
| **1** | Partial match — the intent partially aligns but you'd need to significantly reshape the page |

**Examples:**
- Building a how-to guide → informational keyword → 3
- Building a landing page → transactional keyword → 3
- Building a landing page → informational keyword → 1 (mismatch — users want to learn, not buy)
- Building a comparison post → commercial investigation keyword → 3
- Building a product page → comparison keyword → 2 (product page can include comparison content, but isn't ideal)

---

### Dimension 4: Search volume (contextual, not scored)

Volume is not scored — it's context. A keyword with 50 monthly searches and a score of 10 beats one with 5,000 searches and a score of 5, assuming the 50/month keyword is achievable and relevant.

Volume is used to:
- Estimate traffic potential if ranked in position 1–3 (use CTR of ~25–35% for #1, 10–15% for #2, 7–10% for #3)
- Prioritise between two keywords with identical scores (higher volume wins)
- Flag unrealistically low-volume terms (< 10/month in tools) as "validate after ranking"

---

## Final score calculation

```
Priority Score = (Business relevance × 3) + Achievability + Intent match

Maximum possible score = (3 × 3) + 5 + 3 = 17
```

| Score range | Tier | Action |
|---|---|---|
| 14–17 | Priority 1 — Quick wins | Build first, high confidence |
| 10–13 | Priority 2 — Core targets | Build in months 2–4 |
| 6–9 | Priority 3 — Long-term plays | Plan for months 4–12 |
| 0–5 | Deprioritised | Re-evaluate when authority grows |

---

## Worked examples

**Example A: "HR software for small teams" (KD: 32, vol: 800/mo)**
Scenario: Growing SaaS company, DA 28, building a product landing page

- Business relevance: 3 (transactional, direct product match)
- Achievability: 4 (DA 28 + KD 32 → score 4 per table)
- Intent match: 3 (transactional keyword → landing page is exact match)
- **Priority score: (3×3) + 4 + 3 = 16 → Priority 1**

---

**Example B: "what is employee engagement" (KD: 55, vol: 3,500/mo)**
Scenario: Same company — considering a blog post

- Business relevance: 1 (very top of funnel, loose connection to HR software)
- Achievability: 1 (DA 28 + KD 55 → very low chance)
- Intent match: 3 (informational keyword → blog post is correct format)
- **Priority score: (1×3) + 1 + 3 = 7 → Priority 3 or deprioritised**

Note: High volume is irrelevant here — the site can't rank for it, and those who search it are unlikely to convert.

---

**Example C: "employee engagement software vs culture amp" (KD: 18, vol: 90/mo)**
Scenario: Same company — considering a comparison page

- Business relevance: 3 (comparison/decision stage, direct purchase consideration)
- Achievability: 5 (KD 18 with DA 28 is achievable)
- Intent match: 3 (commercial investigation keyword → comparison page is exact format)
- **Priority score: (3×3) + 5 + 3 = 17 → Priority 1**

Note: Only 90 monthly searches, but extremely high business value and achievable. These keywords consistently punch above their volume weight.

---

## Adjustments and exceptions

**Adjust achievability upward if:**
- You have an existing page with strong authority (internal links + some backlinks) already covering the topic
- The keyword is highly brand-adjacent (your brand name appears in or near the keyword)
- You have topical authority in this specific cluster from adjacent ranking content

**Adjust achievability downward if:**
- The SERP is dominated by major authoritative publishers (Forbes, Hubspot, Wikipedia, etc.) for an informational keyword
- The top results are exact-match domain names (e.g., besthrtools.com for "best HR tools")
- The keyword requires link velocity your site doesn't have

**Override scoring for strategic must-haves:**
Some keywords are strategically important regardless of score — e.g., your brand name, your core product category, your primary competitor comparison. Flag these separately as "strategic must-haves" and plan for them independent of scoring.
