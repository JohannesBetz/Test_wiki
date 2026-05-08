---
tags: [paper]
date: 2026-05-08
task: general_ai
venue: "Book chapter preprint"
sources: 1
year: "2025"
topic:
  - reinforcement_learning
  - embodied_autonomy
  - cognitive_navigation
tech_backbone: [reinforcement_learning]
tech_representation: []
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
simulators_used: []
---

# Welcome to the Era of Experience

> Welcome to the Era of Experience | David Silver and Richard S. Sutton

## Summary

This note argues that the dominant training recipe in AI is shifting. Instead of relying primarily on static human-generated data and human preference signals, future systems will increasingly become strong by learning from their own grounded experience over long time horizons.

The paper frames this as a structural transition in AI, not a niche claim about one algorithm. The idea is that agents can surpass the limits of human-curated data by acting in environments, observing consequences, and iteratively improving from the resulting experience stream.

## Core Argument

The authors contrast two broad eras.

The first is the era of human data, where model improvement comes mostly from imitation, supervision, and human feedback. This has produced impressive general-purpose models, but it is constrained by the scale and quality of what humans already know and can label.

The second is the proposed [[era_of_experience]], where agents learn from interaction. The note argues that this shift will be characterized by:

- Learning over persistent streams rather than short independent episodes.
- Grounded action and observation channels rather than text-only interaction.
- Rewards tied to environmental consequences rather than only human prejudgement.
- Planning and reasoning that are tested against reality rather than only against human discourse.

## Why It Matters

This framing is especially important for robotics and autonomous systems. Domains such as racing, manipulation, theorem proving, science, and tool use are hard to solve from human examples alone because the most valuable data often does not yet exist until the agent explores and creates it.

The paper therefore gives a broad philosophical rationale for many techniques already represented in this vault: RL, self-play, long-horizon strategy learning, grounded reward design, online adaptation, and embodied interaction with the environment.

## Related Work

Within this vault, the paper helps contextualize several otherwise separate lines of work. [[champion_level_drone_racing_using_deep_reinforcement_learning]], [[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]], and [[a_competitor_aware_race_management_policy_a_game_theoretical_approach]] all rely on agents improving through interaction rather than only from demonstrations.

It also resonates with [[machine_survival_a_historical_perspective_on_embodied_autonomous_intelligence]], which argues that intelligence must be understood through embodied coupling with the world, and with [[cognitive_navigation_review]], which frames autonomy as an integrated perception-decision-execution loop.

## Notes / Critique

The note is strongest as a research agenda and synthesis. It names an important limitation of human-data-centric AI and makes a persuasive case that grounded interaction will become more central.

Its limitation is practical specificity. The hard parts of building such agents remain: safe exploration, robust reward grounding, memory over long streams, and reliable autonomy in open-ended real environments.
