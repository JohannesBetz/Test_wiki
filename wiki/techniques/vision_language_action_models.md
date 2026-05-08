---
tags: [technique]
date: 2026-05-08
sources: 1
---

# Vision-Language-Action Models

## Definition

Vision-language-action (`VLA`) models are multimodal policies that use visual observations and language conditioning to predict actions directly. They extend vision-language modeling into embodied control by treating action generation as another modality.

## Key Approach

[[racevla_vla_based_racing_drone_navigation_with_human_like_behaviour]] shows how this idea can be adapted to autonomous drone racing.

In that paper, the VLA receives first-person visual input and natural-language prompts, then predicts low-level drone motion commands. The main idea is not just multimodal understanding, but multimodal control: the model is expected to turn perception and instruction into action without a large explicit intermediate planning stack.

This differs from more classical racing pipelines, where perception, localization, trajectory generation, and control are handled by separate specialized modules.

## Relationship to Embodied Autonomy

This technique belongs near [[foundation_models_for_intelligent_decision_making]], [[end_to_end_autonomous_racing]], and [[autonomous_drone_racing]].

Its promise is broader transfer and easier task conditioning than narrow task-specific controllers. Its risk is that high-speed embodied domains expose latency, distribution shift, and action-reliability failures much more harshly than slower tabletop or manipulation settings.

## Representative Papers

- [[racevla_vla_based_racing_drone_navigation_with_human_like_behaviour]]

## Open Problems

Open problems include inference latency, safe deployment under distribution shift, grounding language commands in real-time control, and deciding how much of the classical robotics stack can be removed before performance collapses in aggressive physical tasks.
