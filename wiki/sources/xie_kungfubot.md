---
tags: [source]
date: 2026-05-26
sources: 1
---

# Xie KungfuBot Source

> Source: `raw/pdfs/Xie_KungfuBot.pdf`
> Paper: KungfuBot: Physics-Based Humanoid Whole-Body Control for Learning Highly-Dynamic Skills, NeurIPS 2025

## Summary

This paper studies how a humanoid can imitate highly dynamic whole-body skills such as Kungfu motions and dancing, where ordinary smooth-motion tracking pipelines typically fail.

For this vault, the paper matters because it gives the humanoid branch a strong `dynamic skill imitation` result rather than only locomotion, hiking, or quasi-static balance.

## Method

The training backbone is [[reinforcement_learning]].

From the paper abstract and project-page support, the framework combines:

- multi-step motion processing to extract, filter, correct, and retarget reference motions,
- adaptive motion tracking through a bi-level optimization formulation,
- and an asymmetric actor-critic training setup.

For this vault, the important point is that KungfuBot treats highly dynamic humanoid skill learning as a reference-processing and adaptive-tracking problem, not only as a reward-design problem.

## Evaluation

The public record reports successful deployment on the Unitree G1 robot with stable and expressive execution of highly dynamic behaviors such as Kungfu and dancing, and significantly lower tracking errors than prior approaches.

For this vault, the useful takeaway is broader than one demonstration:

humanoid whole-body skill learning can scale beyond smooth walking motions when the reference-motion pipeline itself is made adaptive and physically aware.

## Notes / Critique

The strongest contribution is the systems pipeline around motion tracking. The paper does not merely ask a policy to imitate hard motions; it works to make those motions physically trackable first.

That makes it a strong complement to:

- [[hub_learning_extreme_humanoid_balance]], which emphasizes balance-intensive postural skill,
- [[humanoid_parkour_learning]], which emphasizes multi-skill visuomotor parkour,
- and [[perceptive_humanoid_parkour_chaining_dynamic_human_skills_via_motion_matching]], which emphasizes skill composition through motion matching.

## Pages Created From This Source

- [[kungfubot_physics_based_humanoid_whole_body_control_for_learning_highly_dynamic_skills]]
- [[kungfubot]]
