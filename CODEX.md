# Wiki Schema

## Purpose

This wiki tracks research on **Autonomous Systems at the Limits of Handling at high speeds and high acceleration**, with focus on **Autonomous Racing** and **Highly dynamic autonomous systems**. It is a personal research knowledge base built alongside the survey paper:

> *Autonomous Vehicles on the Edge: A Survey on Autonomous Vehicle Racing*
> Johannes Betz et al., IEEE OJ-ITS 2023 — [arXiv:2202.07008](https://arxiv.org/abs/2202.07008)

The wiki accumulates knowledge from individual papers, datasets, and resources covered by the survey, going deeper than the survey itself — noting methodology details, comparing approaches, flagging contradictions, and tracking how the field evolves after the survey's writing cut-off. The wiki further advances the knowledge by searching for new papers that are in other robotics fields like drones, humanoids, quadruped robots that operate with high agility and high speed.

---

## Directory Layout

| Path               | Owner  | Description                                                               |
| ------------------ | ------ | --------------------------------------------------------------------------|
| `raw/`             | User   | Source documents — immutable, never modified by Codex                     |
| `raw/assets/`      | User   | Downloaded images from articles                                           |
| `raw/grants/`      | User   | Existing Grants, summary of grants, full grants, ERC Grants               |
| `Racing-Survey/`   | User   | The survey repo — use as reference but do not modify                      |
| `wiki/`            | Codex | All generated markdown pages                                               |
| `wiki/sources/`    | Codex | One summary page per ingested source, grouped by venue                     |
| `wiki/grant/`      | Codex | One summary page per grant (ERC Grant, DFG Grant)                          |
| `wiki/papers/`     | Codex | Deep-dive pages on individual papers                                       |
| `wiki/models/`     | Codex | Pages for algorithms (LLMs, VLMs, DMs, WMs)                                |
| `wiki/datasets/`   | Codex | Pages for datasets, each with "Papers using this" list                     |
| `wiki/hardware/`   | Codex | Pages for hardware used: Race car, humanoid, quadruped, drone              |
| `wiki/simulators/` | Codex | Pages for simulation platforms, with paper lists                           |
| `wiki/concepts/`   | Codex | FM-type taxonomy only (LLM, VLM, MLLM, DM, WM, VLA)                        |
| `wiki/topics/`     | Codex | Research objectives (algorithms, analysis, deployment, application, etc.)  |
| `wiki/techniques/` | Codex | Cross-cutting methods (diffusion, MPC, RL, )                   |
| `wiki/analyses/`   | Codex | Saved query answers and comparative analyses                               |
| `index.md`         | Codex | Content catalog — updated on every ingest                                  |
| `log.md`           | Codex | Append-only chronological log                                              |

---

## Page Conventions

**Filenames:** snake_case, e.g. `chatscene.md`, `nuscenes_dataset.md`, `scenario_generation_llm.md`

**Internal links:** Obsidian wikilink style — `\[\[page_name\]\]` or `\[\[page_name|display text\]\]`

**Frontmatter** (add to every wiki page):
```yaml
---
tags: [paper|model|dataset|simulator|concept|topic|technique|analysis|source|grant]
date: YYYY-MM-DD
fm_type: LLM|VLM|MLLM|DM|WM            # for paper/model pages
task: autonomous_racing |highly_dynamic_autonomous_system|both  # for paper pages
venue: "CVPR 2026"                       # for paper pages — always "Name YYYY" format
sources: 0                               # number of sources this page draws from

# Paper pages also carry these clustering tags (flat keys — grep-friendly):
topic:                                   # research objectives (one or more)
  - autonomous_racing | high_dynamic | high_agility
  - safety | safety_assessment | safety_verification
  - motion_planning | path_planning | trajectory_planning | optimization
  - control | path_tracking | model_predictive_control
  - foundational_model | reinforcement learning | curriculum_learning
  - applied_robotics | race_cars | drones | robotics | humanoid | quadruped
  - end_to_end_planning | end_to_end_software
tech_backbone: [transformer|vit|cnn|RL]
tech_representation: [bev|occupancy|gaussian_splatting|nerf|sdf|voxel|point_cloud]
tech_generation: [diffusion|rectified_flow|autoregressive|vae|flow_matching|gan]
tech_conditioning: [controlnet|camera_pose_control|text_conditioning|layout_conditioning|trajectory_conditioning]
tech_modality_alignment: [clip_contrastive|cross_modal_attention|q_former|adapter_layers|visual_prompt_tuning]
tech_finetuning: [lora|qlora|grpo|dpo|sft|instruction_tuning|rlhf|full_finetuning]
tech_inference: [cot|icl|rag|few_shot|zero_shot|prompt_engineering|tool_use|agentic]
datasets_used: [nuscenes|waymo|nuplan|navsim|...]
models_used: [gpt4|clip|stable_diffusion|gemini|...]
simulators_used: [carla|metadrive|sumo|waymax]
---
```

**Grant pages** in `wiki/grant/` may additionally use:
```yaml
grant_id: "864042"
acronym: "AGILEFLIGHT"
coordinator: "Davide Scaramuzza"
host_institution: "Universitat Zurich"
start_date: "2020-09-01"
end_date: "2025-08-31"
funding_scheme: "ERC-COG - Consolidator Grant"
total_budget: "2,000,000.00 EUR"
```

**Headings:** Use `##` for top-level sections (page title is `#`).

**Cross-references:** Always wikilink: model names, dataset names, paper nicknames, concept terms. When creating a new page, add backlinks in related existing pages.

**Paper page format:**
```markdown
# Paper Nickname (Year)

> Full title | Venue | `\[\[Author\]\]` et al.

## Summary
## Method
## Key Results
## Datasets Used
## Related Work
## Notes / Critique
```

**Concept page format:**
```markdown
# Concept Name

## Definition
## Key Approaches
## Representative Papers
## Open Problems
```

**Grant page format:**
```markdown
# GRANT_ACRONYM

## Project Metadata
## Objective
## Relevance to the Vault
## Key Project Publications
## Related Models / Topics / Techniques
## Notes
```

---

## Domain Entities

Track these as first-class wiki pages:

| Entity Type | Examples | Wiki directory |
|------------|---------|---------------|
| Papers | ChatScene, ChatSim, LLMScenario | `wiki/papers/` |
| Foundation Models | GPT-4, CLIP, Stable Diffusion, UniAD | `wiki/models/` |
| Datasets | nuScenes, CARLA, Waymo OD | `wiki/datasets/` |
| Simulators | CARLA, SUMO, LGSVL | `wiki/simulators/` |
| Grants | ERC, DFG, Horizon Europe projects | `wiki/grant/` |
| FM-type concepts | LLM, VLM, MLLM, DM, WM | `wiki/concepts/` |
| Research topics | Scenario generation, safety-critical, VQA | `wiki/topics/` |
| Techniques | Diffusion, BEV, LoRA, NeRF, CoT | `wiki/techniques/` |

---

## FM Type Taxonomy

Use these tags consistently across all pages:

- **LLM** — text-only language models (GPT-4, LLaMA, Gemini)
- **VLM** — vision-language models (CLIP, BLIP, GPT-4V)
- **MLLM** — multimodal LLMs with richer modalities
- **DM** — diffusion models (Stable Diffusion, DALL-E)
- **WM** — world models (GAIA-1, DriveDreamer, Vista)

---

## Ingest Workflow

When the user says `ingest raw/<filename>`, follow these steps in order:

1. **Read** the source file at `raw/<filename>`
2. **Discuss** key takeaways — ask about emphasis if the source is long or ambiguous
3. **Write** a summary to `wiki/sources/<slug>.md` with `tags: [source]`
4. **Create or update** entity pages:
   - New paper mentioned → create `wiki/papers/<nickname>.md`
   - New model mentioned → create or update `wiki/models/<model>.md`
   - New dataset mentioned → create or update `wiki/datasets/<name>.md`
   - New research topic introduced → create or update `wiki/topics/<topic>.md`
   - New technique introduced → create or update `wiki/techniques/<technique>.md`
   - New FM-type concept → create or update `wiki/concepts/<concept>.md`
   - Flag contradictions with existing pages using a `> **Contradiction:**` blockquote
5. **Update** `index.md` — add source under `## Sources`; update touched concept/entity entries
6. **Append** to `log.md`:
   ```
   ## [YYYY-MM-DD] ingest | <Source Title>
   Brief note on what was added/changed. Pages touched: X.
   ```

A single source may touch 10–20 wiki pages. That's expected and good.

### Grant Ingest Workflow

When the user says `ingest raw/grants/<filename>`, decide which of these two cases it is:

1. **Grant fact sheet / project summary / award document**
2. **Grant publication list / project bibliography / grant output index**

Then follow the matching workflow:

#### A. Grant fact sheet / project summary

1. **Read** the source file at `raw/grants/<filename>`
2. **Create or update** `wiki/grant/<slug>.md` with `tags: [grant]`
3. Capture the key metadata when recoverable:
   - title
   - acronym
   - grant ID
   - coordinator / PI
   - host institution
   - funding scheme
   - start/end dates
   - total budget
4. Add:
   - `## Objective`
   - `## Relevance to the Vault`
   - `## Key Project Publications` (if known)
   - `## Related Models / Topics / Techniques`
5. **Link the grant page back** into already known funded papers, models, topics, and techniques via a `## Funding / Grants` section where appropriate
6. **Update** `index.md` under `## Grants`
7. **Append** to `log.md`

#### B. Grant publication list / bibliography / output index

1. **Read** the source file at `raw/grants/<filename>`
2. **Create** a source-style registry page in `wiki/sources/<slug>.md` with `tags: [source]`
3. **Update** the corresponding `wiki/grant/<slug>.md` page with a structured publication overview
4. **Create or upgrade** deep paper pages for the most important publications in the grant output
5. **Create or update** technique/model/topic pages that emerge repeatedly from the grant portfolio
6. Add `## Funding / Grants` backlinks on funded paper or model pages when the support relationship is explicit enough
7. **Update** `index.md` under both `## Sources` and `## Grants`
8. **Append** to `log.md`

### Grant Linking Rules

- Use `wiki/grant/` for the grant itself, not `wiki/sources/`
- Use `wiki/sources/` for publication lists, grant bibliographies, or grant-output compilations
- Add `## Funding / Grants` only when the funding relationship is explicit in the source or strongly established by the project context
- Grants are first-class context objects: link them to papers, models, datasets, topics, and techniques when they explain why a research branch exists or coheres
- Prefer one canonical grant page per project acronym or grant ID, then update it over time instead of creating duplicates

---

## Query Workflow

When the user asks a question:

1. Read `index.md` to identify relevant pages
2. Read those pages
3. Synthesize an answer with inline citations (link to paper pages or source summaries)
4. **Offer to file the answer** as `wiki/analyses/<slug>.md` — comparative analyses are reusable

Example queries this wiki is optimized for:
- "What are the main approaches to enable autonomous racing?"
- "Which papers use CARLA for simulation?"
- "What datasets are most commonly used for autonomous racing?"
- "Which papers came out of AGILEFLIGHT or another ERC grant?"
- "Which grant seems to have driven the strongest work on agile drone flight?"

---

## Lint Workflow

When the user says `run a lint pass`, check for:

- **Orphan pages** — pages with no inbound wikilinks
- **Contradictions** — conflicting claims across pages
- **Stale claims** — assertions superseded by newer papers
- **Missing pages** — wikilinks pointing to pages that don't exist yet
- **Missing cross-references** — e.g., a paper page not linked from its concept page
- **Data gaps** — important open questions; suggest papers or resources to find next
- **Taxonomy drift** — FM type tags used inconsistently

Report as a checklist. Offer to fix issues immediately.

---

## Notes

- Never modify files in `raw/` or `Racing-Survey/` — they are the immutable source of truth
- The survey paper (`Racing-Survey/README.md`) is the authoritative paper list; the wiki goes deeper
- Always update `index.md` and `log.md` after any ingest
- Prefer updating existing pages over creating new ones when information naturally belongs there
- When a new paper contradicts or supersedes an existing claim, flag it visibly — do not silently overwrite
