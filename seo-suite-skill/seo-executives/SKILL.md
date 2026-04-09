---
name: seo-executives
description: >
  Orchestrate the full SEO pipeline by intelligently sequencing and routing between all nine SEO sub-skills — seo-strategy-planner, keyword-research-assistant, technical-seo-auditor, on-page-seo-optimizer, link-building-strategist, vertical-seo-specialist, seo-content-brief, international-seo-planner, and seo-stakeholder-pitch — and deliver a consolidated SEO Executive Document (.docx) that captures the inputs, outputs, and recommendations of every module run. Use this skill whenever someone wants end-to-end SEO coverage, a full site SEO program, a board-ready SEO strategy document, or doesn't know where to start with SEO. Also trigger when users say things like "run a full SEO audit", "build me a complete SEO plan", "I need an SEO strategy doc", "cover all angles of SEO for my site", or "what do I need to do to win organic search." This is the top-level SEO skill — always prefer it over individual sub-skills when the scope spans more than one SEO domain.
---

# SEO Executives

The central intelligence layer for the entire SEO program. This skill plans, routes, executes, and documents — it delegates domain expertise to sub-skills but owns the final Executive Document.

---

## System Modules (pipeline order)

| # | Skill | Domain | When to run |
|---|---|---|---|
| 1 | `seo-strategy-planner` | Strategy & foundation | Always — entry point for every program |
| 2 | `keyword-research-assistant` | Keyword targeting | Always — feeds every downstream module |
| 3 | `technical-seo-auditor` | Technical health | Always for existing sites; skip for pre-launch |
| 4 | `on-page-seo-optimizer` | Page-level relevance | Always — applies strategy + keywords to pages |
| 5 | `link-building-strategist` | Authority & backlinks | Always for competitive verticals |
| 6 | `vertical-seo-specialist` | Local / image / video / news | Conditional — run if vertical channels apply |
| 7 | `seo-content-brief` | Content production | Always when content work is planned |
| 8 | `international-seo-planner` | Multi-market expansion | Conditional — run if multiple countries/languages |
| 9 | `seo-stakeholder-pitch` | Executive buy-in | Always when stakeholder alignment is needed |

---

## Deliverable

The SEO Executives skill produces a single consolidated **SEO Executive Document** — a structured `.docx` file built with the `docx` skill. It is the authoritative record of the full SEO program: every module's inputs, outputs, decisions made, and recommended actions.

### Document structure

```
SEO Executive Document — [Site / Company Name]
────────────────────────────────────────────────

Cover page
  - Site / company name
  - Date of analysis
  - Prepared by
  - Executive summary (3–5 sentences: opportunity, key findings, top priorities)

Table of Contents (auto-generated)

Module 1: SEO Strategy
  - Inputs provided
  - Key findings
  - Recommended strategy
  - 90-day priorities

Module 2: Keyword Research
  - Inputs provided
  - Target keyword clusters (table: keyword | intent | volume tier | difficulty | priority)
  - Quick wins vs long-term targets

Module 3: Technical SEO Audit
  - Inputs provided
  - Findings by severity (Critical / High / Medium / Low)
  - Prioritized fix list (table: issue | pages affected | fix | owner | estimated impact)

Module 4: On-Page Optimization
  - Inputs provided
  - Page-by-page recommendations (table: URL | title | meta | H1 | content gaps | internal links)
  - Schema / structured data recommendations

Module 5: Link Building
  - Inputs provided
  - Current backlink profile assessment
  - Recommended strategy and link types
  - Target prospect list or criteria

Module 6: Vertical SEO  [Conditional]
  - Inputs provided
  - Verticals assessed (local / image / video / news / product)
  - Findings and recommendations per vertical

Module 7: Content Briefs
  - Inputs provided
  - Content briefs produced (one per target page/topic)
  - Each brief: target keyword | intent | recommended format | key sections | internal links | success metric

Module 8: International SEO  [Conditional]
  - Inputs provided
  - Markets and languages assessed
  - Hreflang implementation plan
  - Localization priorities

Module 9: Stakeholder Pitch
  - Inputs provided
  - Executive summary of SEO opportunity (business language)
  - ROI framing and timeline
  - Resource requirements and owners
  - Prioritized roadmap (table: initiative | impact | effort | owner | timeline)

Appendix
  - Glossary of SEO terms used in this document
  - Tools referenced
  - Data sources
  - Assumptions log
```

---

## Core Principles

1. **Strategy before tactics** — seo-strategy-planner always runs first; every downstream module inherits its goals.
2. **Keywords are connective tissue** — keyword-research-assistant output feeds modules 3, 4, 5, 7.
3. **Technical before creative** — technical issues suppress everything else; audit before briefs.
4. **Document everything** — every module's input and output is captured verbatim in the Executive Document.
5. **Business language at the top** — module 9 translates all findings into stakeholder-ready narrative.

---

## System Controls

| Control | Options | Default |
|---|---|---|
| **Pipeline Mode** | Auto / Manual | Asked at start |
| **Site Stage** | Pre-launch / Existing / Enterprise | Inferred from intake |
| **Vertical Channels** | Local / Image / Video / News / Product / None | Asked at intake |
| **International** | Yes / No | Asked at intake |
| **Stakeholder Pitch** | Include / Skip | Include |

---

## Workflow

### Phase −2 — Pipeline Mode Gate *(Always first — never skip)*

Ask the user:

> "How do you want to run the SEO pipeline?
>
> **Auto** — I drive everything end-to-end. You answer intake questions upfront and I run all modules in sequence, producing the Executive Document without stopping between steps.
>
> **Manual** — I plan the pipeline and handle intake, then pause. You trigger each step via slash commands (e.g. `/seo-strategy-planner`, `/technical-seo-auditor`, etc.). After each step I'll ask whether to proceed, skip, or re-run before moving forward."

Store as **Pipeline Mode**.

---

### Phase −1 — Site Stage & Scope Gate *(Always — never skip)*

Ask:

> "Before we begin, a few quick scoping questions:
>
> 1. **What is the site/product URL?** (or describe if pre-launch)
> 2. **What stage is the site?** Pre-launch / Existing site / Enterprise / Not sure
> 3. **Do any vertical channels apply?** (select all that apply) Local/Maps · Image search · Video (YouTube or embedded) · Google News · Product/Shopping · None
> 4. **Are you targeting multiple countries or languages?** Yes / No
> 5. **Do you need a stakeholder pitch?** Yes / No
>
> You can answer all at once or I can ask one at a time."

Store all answers. They determine which modules run and in what configuration.

---

### Phase 0 — Input Intake & Classification

Classify the site's SEO starting point:

| Level | Description | Entry adjustment |
|---|---|---|
| **Pre-launch** | No site yet | Skip technical audit; run strategy → keywords → on-page → content brief |
| **Early site** | Launched < 12 months, little organic presence | Full pipeline |
| **Established site** | Existing traffic, wants to grow | Full pipeline with audit as top priority |
| **Enterprise** | Multiple teams, large site, competitive vertical | Full pipeline + stakeholder pitch is mandatory |

---

### Phase 1 — Completeness Evaluation

Assess what data the user has already provided:
- Site URL and access to Google Search Console or crawl data
- Existing keyword targets or content inventory
- Known technical issues
- Competitor names
- Business goals and primary conversion event
- Budget and resource constraints

**Output:** list of missing data → determine what will be assumed vs. asked.

---

### Phase 2 — Global Intake Questioning

Bundle all cross-module questions into a single intake. Never repeat questions per module.

**Always ask:**
- Primary conversion goal (purchase / lead / signup / ad revenue / brand)
- Top 3 competitors in organic search
- Primary target audience (who searches for what they offer)
- Current organic traffic status (growing / flat / declining / unknown)
- Content team capacity (heavy / light / none)

**Ask only if applicable:**
- Target countries and languages (if international = yes)
- Primary local service area (if local = yes)
- YouTube channel or video inventory (if video = yes)
- Google News eligibility (news / editorial site only)

---

### Phase 3 — Execution Planning

Define the pipeline dynamically based on site stage, scope gates, and available data.

```
Full pipeline (existing site, all channels):
  seo-strategy-planner → keyword-research-assistant → technical-seo-auditor
  → on-page-seo-optimizer → link-building-strategist → vertical-seo-specialist
  → seo-content-brief → international-seo-planner → seo-stakeholder-pitch

Pre-launch pipeline:
  seo-strategy-planner → keyword-research-assistant → on-page-seo-optimizer
  → link-building-strategist → seo-content-brief → seo-stakeholder-pitch

No international, no vertical:
  seo-strategy-planner → keyword-research-assistant → technical-seo-auditor
  → on-page-seo-optimizer → link-building-strategist → seo-content-brief
  → seo-stakeholder-pitch
```

#### If Pipeline Mode = Manual

Output the **Manual Pipeline Roadmap**:

```
SEO Executive Pipeline — [Site Name]
──────────────────────────────────────────
Step 1 → /seo-strategy-planner
Step 2 → /keyword-research-assistant
Step 3 → /technical-seo-auditor
Step 4 → /on-page-seo-optimizer
Step 5 → /link-building-strategist
Step 6 → /vertical-seo-specialist        [if applicable]
Step 7 → /seo-content-brief
Step 8 → /international-seo-planner      [if applicable]
Step 9 → /seo-stakeholder-pitch
──────────────────────────────────────────
Context passes between steps automatically.
Run the first command when ready: /seo-strategy-planner
```

Then **pause**. Do not run any module. Wait for the user's slash command.

---

### Phase 4 — Module Execution

#### Auto Mode

For each module in the planned pipeline:

```
1. INPUTS   → load sub-skill; inject prior module outputs + global intake data
2. RUN      → invoke the sub-skill; follow its full workflow
3. CAPTURE  → record: inputs provided, key findings, outputs, decisions made
4. VALIDATE → check output completeness before passing forward
5. LOG      → append captured data to the Executive Document draft
6. SURFACE  → show user a 3-bullet summary; ask to proceed or refine
```

**Never skip validation.** Broken output from one module must not corrupt downstream modules.

#### Manual Mode

When the user invokes a slash command:

```
1. CONTEXT CHECK  → confirm step is next in pipeline; warn if out of order
2. INPUTS         → inject all prior module outputs + global assumptions
3. RUN            → invoke the sub-skill fully
4. CAPTURE        → inputs, findings, outputs, decisions
5. VALIDATE       → completeness check
6. LOG            → append to Executive Document draft
7. STEP GATE      → show completion message + next step
```

After each manual step, show:

> **[Module name] complete.** Next: `[/slash-command]`
> 
> Proceed / Skip / Re-run / Adjust inputs

---

### Phase 5 — Context Passing Rules

Each module receives structured context from all prior modules:

| Receiving module | Must receive from prior modules |
|---|---|
| `keyword-research-assistant` | Strategy goals, target user, competitors |
| `technical-seo-auditor` | Site URL, keyword priorities |
| `on-page-seo-optimizer` | Target keywords per URL, strategy goals |
| `link-building-strategist` | Keyword targets, competitor backlink profiles |
| `vertical-seo-specialist` | Strategy, keywords, applicable channels |
| `seo-content-brief` | Keyword clusters, on-page findings, content gaps |
| `international-seo-planner` | Strategy, keywords, technical audit findings |
| `seo-stakeholder-pitch` | Outputs from ALL prior modules |

---

### Phase 6 — Conflict Resolution

If two modules produce conflicting recommendations:

**Authority order (higher = wins):**
1. seo-strategy-planner (business goals override everything)
2. technical-seo-auditor (crawl/index health is foundational)
3. keyword-research-assistant (keyword data is source of truth)
4. on-page-seo-optimizer
5. link-building-strategist
6. vertical-seo-specialist
7. seo-content-brief
8. international-seo-planner
9. seo-stakeholder-pitch

Log all resolved conflicts in the document's Assumptions Log.

---

### Phase 7 — Progress Tracking

Show this tracker after each module completes. Update in-place:

```
SEO Executive Pipeline — [Site Name]
──────────────────────────────────────────
✅ SEO Strategy            — complete
✅ Keyword Research         — complete
⏳ Technical Audit          — in progress
⬜ On-Page Optimization     — pending
⬜ Link Building            — pending
⬜ Vertical SEO             — pending
⬜ Content Briefs           — pending
⬜ International SEO        — pending
⬜ Stakeholder Pitch        — pending
⬜ Executive Document       — pending
──────────────────────────────────────────
```

---

### Phase 8 — Pre-Document Consistency Check

Before assembling the Executive Document, verify:

- All module outputs reference the same site/product ✅/❌
- Keyword targets are consistent across on-page, content briefs, and link strategy ✅/❌
- Technical fixes align with on-page recommendations (no contradictions) ✅/❌
- Content briefs map to keyword clusters from keyword research ✅/❌
- Stakeholder pitch uses business language (no unexplained jargon) ✅/❌
- All conditional modules (vertical, international) are either complete or explicitly skipped with reason ✅/❌

Resolve all ❌ before producing the document.

---

### Phase 9 — Executive Document Production

Invoke the `docx` skill. Build the SEO Executive Document per the structure defined above.

**Document production rules:**
- Use the site/company name in the document title and cover page
- Every module section must contain: **Inputs**, **Findings**, **Recommendations**, and a **Priority Action** callout box
- Tables for: keyword targets, technical issues, on-page recommendations, content briefs, roadmap
- Conditional modules (vertical, international) appear only if they were run; otherwise include a single-line note: *"[Module name] — not applicable for this engagement"*
- Assumptions log in the appendix captures every case where data was missing and an assumption was made
- Executive summary on the cover page must be written in non-technical business language
- Final page: **30-Day Quick Win Plan** — top 5 highest-impact, lowest-effort actions from across all modules

Invoke `docx` skill:
```
1. Read /mnt/skills/public/docx/SKILL.md
2. Build the document with full structure above
3. Save to /mnt/user-data/outputs/seo-executive-document-[site-name].docx
4. Call present_files with the output path
```

---

## Output Format (Per Session)

```
### Pipeline Progress
[progress tracker — ✅ / ⏳ / ⬜ per module + document]

### Module Summaries
- seo-strategy-planner:       [3-bullet summary]
- keyword-research-assistant: [3-bullet summary]
- technical-seo-auditor:      [3-bullet summary]
- on-page-seo-optimizer:      [3-bullet summary]
- link-building-strategist:   [3-bullet summary]
- vertical-seo-specialist:    [3-bullet summary or SKIPPED]
- seo-content-brief:          [3-bullet summary]
- international-seo-planner:  [3-bullet summary or SKIPPED]
- seo-stakeholder-pitch:      [3-bullet summary]

### Conflicts Resolved
[Conflict] → [Resolution]

### Assumptions Made
[Missing data point] → [Assumption used]

### Executive Document
[present_files link to .docx]
```

---

## Constraints

- **Pipeline Mode gate is mandatory** — ask before scope gate, before any SEO work
- **Scope gate is mandatory** — ask before any module runs; determines which modules are included
- **Progress tracker is mandatory** — show after every module, update in-place
- **Context passing is mandatory** — every module receives structured output from all prior modules
- **Validation between modules is mandatory** — never pass incomplete or broken output forward
- **Document every input and output** — the Executive Document is the single source of truth for the engagement
- **No jargon in the stakeholder pitch** — all findings must be translated into business outcomes
- **Assumptions log must be maintained** — every assumption must be flagged and logged
- **Sub-skill SKILL.md files must be loaded** — read each sub-skill before invoking it
- **docx skill must be loaded** — read `/mnt/skills/public/docx/SKILL.md` before building the document
- **Manual mode: re-run always regenerates the document section** for that module before proceeding
- Always optimize for: completeness, cross-module coherence, business clarity

---

## Tone & Style

- **Executive during planning** — decisive, no fluff, clear scope
- **Technical during module execution** — precise, data-referenced, actionable
- **Business-language during document production** — every finding framed as an opportunity or risk with revenue/traffic implication
- **Consultative throughout** — this is a full SEO program, not a checklist

---

## Decision Rules

- Always ask Pipeline Mode first — before scope gate, before any module
- Site stage = pre-launch → skip technical-seo-auditor; note in document
- Vertical channels = none → skip vertical-seo-specialist; note in document
- International = no → skip international-seo-planner; note in document
- Stakeholder pitch = no → skip seo-stakeholder-pitch; note in document
- Any module fails or returns insufficient data → log assumption, continue pipeline
- Conflicting module outputs → authority order wins; log resolution
- Always show progress tracker so the user knows exactly where they are
- Final deliverable is always the `.docx` Executive Document — never just inline text
