---
tags: [paper]
date: 2026-05-13
task: ai_systems
venue: "arXiv 2024"
sources: 1
year: "2024"
topic:
  - foundation_models_for_intelligent_decision_making
  - embodied_autonomous_intelligence
  - real_world_robotic_foundation_models
tech_backbone: []
tech_representation: []
tech_generation: [foundation_models_for_intelligent_decision_making]
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
hardware_used: [multiple_robot_embodiments]
simulators_used: []
---

# Towards General-Purpose Robots via Foundation Models: A Survey and Meta-Analysis

> Towards General-Purpose Robots via Foundation Models: A Survey and Meta-Analysis | arXiv 2024 | Jonathan Francis et al.

## Summary

This paper surveys how foundation models are being used in robotics with the explicit goal of understanding whether they can move the field toward more general-purpose robots.

Its central value for this vault is conceptual: it asks not only where foundation models help, but what kinds of robotic generality they actually enable across tasks, embodiments, and system architectures.

## Method

The paper is a survey and meta-analysis of foundation-model-based robotics work.

That framing matters because the field can otherwise look fragmented: vision-language-action systems, language-conditioned planning, multimodal policy learning, and robot reasoning assistants often appear as disconnected lines of work. A meta-analysis helps identify what these approaches share, where they differ, and which claims of generality are currently well supported.

## Key Results

For this vault, the key result is the field-level synthesis. The paper provides a structured view of how foundation models may contribute to more general robotic competence, while also exposing the gap between broad pretrained priors and the harder requirements of embodied deployment.

It therefore strengthens the idea that "general robots" will likely require more than just larger models. They will also require careful interfaces to sensing, action, memory, planning, safety, and task grounding.

## Hardware Used

- [[multiple_robot_embodiments]]


## Related Work

This paper belongs near [[real_world_robotic_foundation_models]], but it plays a different role from [[real_world_robot_applications_of_foundation_models_a_review]]. The Kawaharazuka review is a deployment filter: what works on physical robots today. This paper is a strategic synthesis: what the whole foundation-model robotics movement seems to be converging toward.

It also fits naturally with [[foundation_models_for_intelligent_decision_making]] and [[embodied_autonomous_intelligence]], where the central question is how broad priors and embodied constraints can be made to cooperate rather than compete.

Compared with [[racevla_vla_based_racing_drone_navigation_with_human_like_behaviour]], this paper is obviously much broader, but it gives context for why VLA-like approaches are seen as steps toward robotic generality rather than just isolated multimodal controller demos.

## Notes / Critique

The strongest contribution is organizational clarity. The paper helps interpret a fast-moving field without collapsing every foundation-model robotics result into the same bucket.

For this vault, that is useful because it balances ambition and realism: it keeps the "general robots" agenda visible while still leaving room for the harsher lessons from real-world deployment papers.
