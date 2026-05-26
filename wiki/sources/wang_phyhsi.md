---
tags: [source]
date: 2026-05-26
sources: 1
---

# Wang PhyHSI Source

> Source: `raw/pdfs/Wang_PhyHSI.pdf`
> Paper: PhysHSI: Towards a Real-World Generalizable and Natural Humanoid-Scene Interaction System, arXiv 2025

## Summary

This paper studies how a humanoid can interact naturally with real scenes rather than only replaying motions in empty space or traversing terrain in narrowly structured setups.

For this vault, it matters because it pushes the humanoid branch from locomotion, parkour, and balance toward full humanoid-scene interaction under real-world sensing and deployment constraints.

## Method

The training backbone is [[reinforcement_learning]].

The paper centers on [[physhsi]], a humanoid-scene interaction system built around:

- AMP-style humanoid policy learning from motion priors,
- sim-to-real transfer and robustness engineering,
- and a real deployment stack with onboard scene perception and localization.

For this vault, the important point is that the paper treats natural interaction not as a pure animation problem, but as a systems problem that joins learned whole-body behavior with real scene grounding.

## Evaluation

The public record reports deployment on the Unitree G1 humanoid across scene-interaction tasks supported by real-world perception and localization.

The broader takeaway is that humanoid competence is starting to move beyond walking and obstacle traversal toward more natural full-body behavior in everyday scenes.

## Notes / Critique

The strongest contribution is architectural breadth. This paper is useful less because it introduces one tiny new control trick and more because it frames `generalizable humanoid-scene interaction` as a stack problem spanning policy prior, embodiment, and perception.

That makes it a strong complement to:

- [[real_world_humanoid_locomotion_with_reinforcement_learning]], which is more locomotion-centric,
- [[humanoid_parkour_learning]], which is more agility- and traversal-centric,
- and [[kungfubot_physics_based_humanoid_whole_body_control_for_learning_highly_dynamic_skills]], which is more dynamic-motion-imitation-centric.

## Pages Created From This Source

- [[physhsi_towards_a_real_world_generalizable_and_natural_humanoid_scene_interaction_system]]
- [[physhsi]]
