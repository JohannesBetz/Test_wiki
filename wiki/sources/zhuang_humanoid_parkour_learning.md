---
tags: [source]
date: 2026-05-22
sources: 1
---

# Zhuang Humanoid Parkour Learning Source

> Source: `raw/pdfs/Zhuang_Humanoid_Parkour_Learning.pdf`
> Paper: Humanoid Parkour Learning, CoRL 2024

## Summary

This paper studies how a humanoid can learn one end-to-end visuomotor policy that covers several parkour-style traversal skills instead of relying on trajectory optimization for one fixed obstacle course or on motion priors for one narrow maneuver.

For this vault, the paper matters because it gives the humanoid branch a learning-first parkour result that contrasts nicely with the newer motion-matching formulation.

## Method

From the title, keywords, and public record, the system is a vision-based whole-body-control parkour policy learned through [[reinforcement_learning]] with a sim-to-real transfer pipeline.

For this vault, the important point is that the policy is framed as:

- end-to-end,
- visuomotor,
- whole-body,
- and multi-skill

rather than as a hand-stitched planner for one pre-scripted obstacle sequence.

## Evaluation

According to the public abstract, the policy enables a humanoid to jump onto elevated platforms, leap over hurdles and gaps, run in the wild, and traverse different indoor and outdoor terrains while following joystick commands.

For this vault, the key result is breadth of maneuvering within one policy: parkour-like traversal is treated as a unified real-world skill family rather than a sequence of separately engineered demos.

## Notes / Critique

The strongest contribution is the single-policy framing. It pushes the humanoid branch toward a stronger claim that one learned controller can cover a meaningful range of aggressive traversal behaviors.

That makes it a strong complement to:

- [[perceptive_humanoid_parkour_chaining_dynamic_human_skills_via_motion_matching]], which emphasizes explicit dynamic skill chaining,
- [[real_world_humanoid_locomotion_with_reinforcement_learning]], which emphasizes real-world humanoid locomotion as a baseline success case,
- and [[attention_based_map_encoding_for_learning_generalized_legged_locomotion]], which emphasizes terrain representation across embodiments.

## Pages Created From This Source

- [[humanoid_parkour_learning]]
