# Video generation director

Structured **skill** (and reference pack) for high-performing **video ads**: creative briefs, scene-by-scene specs, and **copy-ready prompts** for generative video tools. Licensed under the [MIT License](LICENSE).

## What you get

- **[SKILL.md](SKILL.md)** — Full workflow: inputs, steps, markdown **output modes**, constraints, and links to all knowledge files.
- **`foundations/`** — Shot types, camera, composition, lighting.
- **`ad-patterns/`** — Hooks, product shots, emotional sequences, story structures.
- **`high-performing-formats/`** — TikTok, YouTube, and cinematic pacing rules.
- **`templates/`** — `production_brief` / `prompts_only` / `both` helpers and platform-flavored prompt shells.

## How to use this skill

1. **Open or copy** this repository into the workspace you use for the project.
2. **Load the skill** — Attach or paste [SKILL.md](SKILL.md) into your AI assistant (or your team’s prompt library) and ask it to follow that document for the ad you are building. You can also add it to your own **project rules** or **system instructions** so video-ad tasks always use the same workflow.
3. **Provide inputs** (see **input** in [SKILL.md](SKILL.md)):
   - `platform`, `objective`, `product`, `audience`, `emotion`, `hook_type`
   - **`output_preference`:** `production_brief` (brief only), `prompts_only` (prompts only), or `both` (default if omitted — see skill text).
4. **Use the output** — Paste **prompts** into your video tool; hand **production briefs** to editors, producers, or storyboard artists.

**Manual use:** Treat [SKILL.md](SKILL.md) as a **checklist and spec**. Fill [templates/universal-template.md](templates/universal-template.md) (or the TikTok / YouTube / cinematic variants) by hand or in any editor.

## Supported video generation tools

This skill is **tool-agnostic**: it emits **markdown** (briefs and/or text prompts). Any product that accepts natural-language or structured scene descriptions can use it. Compatibility depends on each tool’s **prompt length, aspect ratios, duration caps, and safety filters** — always trim or split prompts to fit.

| Tool / family | Typical use with this repo | Notes |
|---------------|-----------------------------|--------|
| **Runway** (Gen-3, etc.) | Scene prompts, camera/lighting language | Strong for short clips; align duration/aspect to your plan. |
| **Pika** | Text-to-video segments from scene blocks | Good for stylized ads; may need shorter scenes per generation. |
| **Luma Dream Machine** | Cinematic motion from descriptive scenes | Useful for B-roll and mood shots. |
| **Kling** (and similar) | Same pattern: one scene or beat per prompt | Check regional availability and ToS. |
| **Google Veo** / **OpenAI Sora** (where available) | Longer-form or higher fidelity from detailed briefs | Access and limits change; treat as optional. |
| **Haiper**, **PixVerse**, **others** | Per-clip generation from **Scene** sections | Iterate clip-by-clip, then edit in NLE. |
| **Traditional pipeline** | **Production brief** only → storyboard / shoot / edit | No Gen-AI required. |

**Not officially affiliated** with any vendor above. Names are for orientation only; capabilities change frequently.

## Unexplored: MCP and API integrations

This repository today is **files + markdown only**: there is **no** bundled MCP server, CLI, or HTTP service. Everything below is **intentionally open** — useful if you want to automate the gap between **SKILL.md output** and **vendor APIs**.

### Model Context Protocol (MCP)

Possible directions no one has wired up here yet:

- **Knowledge as tools** — Expose `foundations/`, `ad-patterns/`, and `high-performing-formats/` as MCP *resources* or small *tools* (e.g. “return TikTok pacing rules”) so an assistant pulls only the slice it needs instead of loading the whole tree.
- **Structured brief I/O** — A tool that accepts the skill’s **input** fields (platform, emotion, hook_type, `output_preference`, etc.) and returns **validated JSON** (scene list, timings, CTA) for downstream steps.
- **Template merge** — A tool that fills `templates/*.md` placeholders from a brief and returns **ready-to-POST** prompt strings per scene or per platform.
- **Pipeline glue** — Tools that read/write a shared **job manifest** (brief ID, scene index, prompt hash, asset URLs) so humans and agents see the same state across sessions.
- **Brand / asset context** — Optional MCP resources pointing at **DAM URLs**, font packs, or legal lines so generated prompts stay on-brand without duplicating secrets in chat logs.

*Caveats:* API keys, rate limits, and provider ToS stay **your** responsibility; any MCP layer should enforce **redaction** and **opt-in** submission to external services.

### REST or vendor APIs

Same story in “plain HTTP” form — not implemented here, but a natural fit:

- **POST /brief** — Body = skill inputs → response = `{ production_brief_md, prompts_md }` or normalized **scene[]** for a render queue.
- **Adapter modules** — One function per vendor: map a **Scene** object to that API’s prompt shape, duration, aspect ratio, and negative prompts.
- **Async jobs** — Submit clips, poll or **webhook** on completion, append results (file URLs, generation IDs) back into a **production log** markdown or JSON.
- **Evaluation loop** — Store export metadata (length, hook window, caption safe area) for A/B tests or human QC checklists.

### Why this is still “unexplored”

- **No canonical JSON schema** in-repo yet (markdown is the source of truth).
- **No auth, queue, or storage** — you would add those in your own app or agent host.
- **Vendor APIs diverge** quickly; a thin **adapter** layer ages better than hard-coding one product.

If you build an MCP server or an API shim on top of this skill, consider publishing it as a **separate** package and linking back here for the creative rules.

## Room for improvement

Contributions and ideas are welcome (see [LICENSE](LICENSE)). Sensible next steps:

- **Per-tool prompt packs** — Short addenda for Runway vs Pika vs Luma (max tokens, default aspect, “do / don’t” per API).
- **Locales & compliance** — Regional claims, subtitles, and legal supers as optional fields in the brief.
- **Metrics hooks** — Optional section tying hooks to testable hypotheses (CTR, hold rate) without overfitting.
- **More platforms** — Meta Reels, Shorts, OTT pre-roll, etc., as separate `high-performing-formats` files.
- **Versioning** — Changelog when format rules or scene schema change.
- **Examples** — Anonymized sample brief + prompt pair for each `output_preference`.
- **JSON schema** — Formal scene/brief types so MCP tools and HTTP APIs can validate payloads without scraping markdown.

If you extend the knowledge files, keep **[SKILL.md](SKILL.md) `knowledge_references`** links in sync.
