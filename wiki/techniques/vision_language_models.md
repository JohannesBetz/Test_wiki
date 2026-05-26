---
tags: [technique]
date: 2026-05-13
sources: 1
---

# Vision-Language Models

## Definition

Vision-language models (`VLMs`) are multimodal foundation models that jointly process visual inputs and language, enabling grounding, open-vocabulary perception, multimodal reasoning, and instruction-conditioned interpretation.

## Key Role in This Vault

In this vault, `VLMs` are best understood as a bridge between abstract language reasoning and embodied control.

They are more grounded than [[large_language_models]] because they see visual context, but they usually stop short of direct low-level action prediction. That makes them especially relevant for perception, scene understanding, and task grounding in autonomous systems.

## Relationship to Robotics and High-Speed Autonomy

This technique belongs near [[foundation_models_for_intelligent_decision_making]] and [[real_world_robotic_foundation_models]].

Compared with [[vision_language_action_models]], `VLMs` are usually one step farther away from direct control. Their contribution is often to improve understanding and context rather than to close the action loop by themselves.

## Representative Papers

- [[foundation_models_in_robotics_applications_challenges_and_the_future]]
- [[real_world_robot_applications_of_foundation_models_a_review]]

## Open Problems

Open problems include latency, grounding under visual ambiguity, robustness under distribution shift, and deciding how VLM outputs should interface with planners and controllers in real-time embodied systems.
