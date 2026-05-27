---
tags: [technique]
date: 2026-05-13
sources: 2
---

# Large Language Models

## Definition

Large language models (`LLMs`) are foundation models trained primarily on text that can generate, transform, and reason over language, code, and other symbolic sequences.

## Key Role in This Vault

In this vault, `LLMs` matter less as direct high-speed controllers and more as high-level reasoning or decision-support components.

[[human_vs_machine_behavioral_differences_between_expert_humans_and_language_models_in_wargame_simulations]] gives a useful cautionary example: an LLM may sound strategically plausible while still diverging from expert-human behavior in ways that matter operationally.

[[exgrpo_learning_to_reason_from_experience]] adds a more optimistic training-side example: if reasoning quality is one of the main bottlenecks, then LLMs may improve not only through larger corpora or better prompting, but through explicitly experience-centered optimization.

## Relationship to Robotics and High-Speed Autonomy

This technique belongs near [[foundation_models_for_intelligent_decision_making]] and the broader foundation-model branch.

Compared with [[vision_language_models]], `LLMs` are less grounded in visual input. Compared with [[vision_language_action_models]], they are much farther from low-level embodied control.

## Representative Papers

- [[human_vs_machine_behavioral_differences_between_expert_humans_and_language_models_in_wargame_simulations]]
- [[exgrpo_learning_to_reason_from_experience]]

## Open Problems

Open problems include grounding, robustness of multi-step reasoning, behavioral calibration in high-stakes settings, and deciding how much authority language-only models should have in embodied systems with severe real-time constraints.
