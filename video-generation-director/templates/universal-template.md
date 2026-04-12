# Universal AI video generation — prompt template

**Output preference for the assistant that writes your deliverable:** `[production_brief | prompts_only | both]` — see [output-modes.md](output-modes.md). This file is the **prompts** portion; if you use `production_brief`, you only need the scene/overview structure from [SKILL.md](../SKILL.md), not this START/END block.

Replace every `[BRACKETED]` value, then copy **from START through END** into any text-to-video or image-to-video tool (or into a chat that will turn this into shots).

---

## START PROMPT

You are a creative director generating a single coherent video ad. Follow the brief exactly. Every shot must specify: shot type, camera movement, composition, lighting, what happens on screen, and why it matters for the story or conversion. Do not repeat the same shot grammar in consecutive scenes unless the platform rules require it.

**Platform:** [tiktok_ads | youtube_ads | cinematic_ads]  
**Aspect / length (if applicable):** [e.g. 9:16, 15–30s]  
**Objective:** [sell | leads | awareness | installs | other]  
**Product:** [name + one-line description]  
**Audience:** [who they are + context]  
**Emotion arc:** [problem_to_relief | aspiration | social_proof | fomo_sequence | discovery | transformation_arc | status_signal]  
**Hook type:** [pattern_interrupt | direct_address | curiosity_gap | problem_opening | bold_claim | before_after_hook | visual_shock]  
**Story structure (optional):** [e.g. hook_story_offer | problem_solution | AIDA — or “choose best fit”]  
**Brand / tone:** [words to match]  
**Must-show:** [product moments, legal line, logo, etc.]  
**Avoid:** [claims, visuals, or styles to skip]

**Platform execution (apply strictly):**

- If **tiktok_ads:** hook in 0–2s; very fast pacing (~1–2s per visual idea); handheld/POV-friendly; captions assumed; visual change ~every 2s; no slow cinematic intro.
- If **youtube_ads:** hook in 0–5s to beat skip; pattern interrupt every 5–10s; mix story + product; clear payoff before CTA.
- If **cinematic_ads:** slower, intentional pacing; emotion-first; minimal on-screen text; wide/macro/slow-mo acceptable; strong mood and music implied.

**Output format (use these headings and fill every field):**

### Overview

- **Platform:**
- **Objective:**
- **Emotion:**
- **Hook:**
- **Product:**
- **Audience:**

### Scene 1

- **Time:**
- **Shot_Type:**
- **Camera:**
- **Composition:**
- **Lighting:**
- **Pattern_Used:**
- **Description:** (what we see and hear)
- **Purpose:**

### Scene 2

- **Time:**
- **Shot_Type:**
- **Camera:**
- **Composition:**
- **Lighting:**
- **Pattern_Used:**
- **Description:**
- **Purpose:**

### Scene 3

- **Time:**
- **Shot_Type:**
- **Camera:**
- **Composition:**
- **Lighting:**
- **Pattern_Used:**
- **Description:**
- **Purpose:**

### Scene 4 (optional — add Scene 5, 6… if length requires)

- **Time:**
- **Shot_Type:**
- **Camera:**
- **Composition:**
- **Lighting:**
- **Pattern_Used:**
- **Description:**
- **Purpose:**

### Final scene

- **Time:**
- **Shot_Type:**
- **Camera:**
- **Composition:**
- **Lighting:**
- **Pattern_Used:**
- **Description:**
- **CTA:** (spoken, on-screen, or implied)

After the scenes, add one short line: **Music / sfx note:** [tempo, vibe, key hit for CTA].

## END PROMPT
