---
name: ads-strategy-discovery-deliverables
description: Runs paid ads strategy discovery and deliverable generation for business users. Use when the user asks for ads strategy, paid ads planning, platform recommendation, campaign direction, or marketing deliverables. Guides back-and-forth business questioning, chooses channels if the user is unsure, and requires exploring project data and logic files before producing output.
---
# Ads Strategy Discovery Deliverables

## Purpose

Use this skill to produce higher-quality paid ads strategy outputs by forcing a clear discovery flow before recommendations.

## Workflow

Follow this sequence every time.

### 1) Discovery First (Back-and-Forth Questions)

Start with short, practical questions about the business. Ask only what is missing.

Required discovery fields:
- Business type and offer
- Target customers (ICP/persona)
- Geography and language
- Budget range and timeline
- Funnel stage (awareness, lead gen, sales)
- Current channels and past results
- Main business problem to solve
- Primary goal and success metric

If the user response is vague, ask follow-up questions until each field is usable.

### 2) Clarify What User Really Wants

Before strategy, restate in one sentence:
- The user problem
- The desired business outcome
- The key constraint (budget/time/team/compliance)

If the user confirms, proceed. If not, refine and confirm again.

### 3) Platform Selection Logic

If user already chose a platform, validate fit briefly.

If user does not know what platform to use, select using this default logic:
- **Google Ads first** when demand already exists and intent capture matters (search-driven buying behavior).
- **LinkedIn Ads first** for B2B professional targeting, longer sales cycles, and lead quality needs.
- **Hybrid** when both intent capture and professional demand shaping are needed.

When suggesting a platform, always include:
- Why this platform fits the business problem
- What trade-off is accepted (cost, speed, lead quality, scale)
- What to test in first 30 days

### 4) Required Internal Exploration

Before final recommendations, explore relevant local files:
- `logic/*.md`
- `data/*.md`

Extract reusable insights:
- Proven tactics
- Case-study patterns
- Risk flags
- Benchmarks

Do not produce a final strategy without this exploration step.

### 5) Build Deliverables

Generate outputs in markdown with clear sections and action steps.

Minimum deliverables:
1. Executive summary
2. Channel strategy
3. Creative/testing plan
4. Funnel optimization plan
5. Measurement framework
6. 30-60-90 day action plan

## Output Standard

For every recommendation, include:
- Decision
- Why it matters
- How to execute
- How success is measured

Use concise bullets and practical language. Avoid generic marketing advice.

## Guardrails

- Never skip discovery just because the user asked for quick output.
- Never assume platform fit without stating assumptions.
- Never provide scaling advice without measurement basics.
- Prefer specific steps over abstract frameworks.

## Fast Template

Use this structure when drafting:

```markdown
# [Client/Project] Paid Ads Strategy

## Business Context
- Offer:
- Audience:
- Problem:
- Goal:

## Platform Direction
- Recommended platform(s):
- Why:
- First 30-day test:

## Strategy and Execution
- Campaign structure:
- Creative approach:
- Funnel approach:
- Optimization rhythm:

## Measurement
- KPI stack:
- Tracking requirements:
- Decision thresholds:

## 30-60-90 Plan
- Days 1-30:
- Days 31-60:
- Days 61-90:
```
