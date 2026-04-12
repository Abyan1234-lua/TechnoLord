# Output modes (markdown)

Set **`output_preference`** in the brief (see [SKILL.md](../SKILL.md) **input**). The assistant responds in **Markdown** using **one** of the layouts below.

---

## `production_brief`

Creative / editorial document **only**. No “You are a…” or tool **prompt** wrapper.

Use headings:

- `## Production brief`
- `### Overview` — platform, objective, emotion arc, hook strategy, product, audience, key message, aspect & duration, **Output preference:** `production_brief`
- `### Strategy & creative` — insight, story structure, tone, must-show / avoid
- `### Platform execution` — pacing, structure, captions/VO/supers
- `### Scene breakdown` — per scene: Time, Shot type, Camera, Composition, Lighting, Pattern, **Action** (editorial), Purpose; final scene includes **CTA**
- `### Audio` — music / sfx
- `### Deliverables` — checklist

---

## `prompts_only`

**Only** copy-ready prompt(s). Optional one-line recap at top.

Use headings:

- `## Prompts (copy-ready)`
- **Output preference:** `prompts_only`
- `### Primary prompt` — full text to paste into a video AI (instructions + constraints + scene output schema)
- Optional: `### Scene N prompt` — extra self-contained blocks

Do **not** include a full production brief section.

---

## `both`

Two parts in **one** markdown reply, brief first.

1. `## Production brief` — same content as `production_brief` mode  
2. A line with only `---`  
3. `## Prompts (copy-ready)` — same as `prompts_only` primary prompt (standalone if the tool has no chat history; otherwise may reference “use the production brief above”)

**Output preference:** `both` in Overview.

---

## Scene fields (shared)

| Field | Brief label | Inside prompt |
|--------|-------------|----------------|
| Time | Time | Time |
| Shot grammar | Shot type | Shot_Type |
| Camera | Camera | Camera |
| Composition | Composition | Composition |
| Lighting | Lighting | Lighting |
| Pattern | Pattern / shot grammar | Pattern_Used |
| What happens | Action | Description |
| Why | Purpose | Purpose |
| End | CTA | CTA |

Default if user omits preference: **`both`**, stated once in Overview.
