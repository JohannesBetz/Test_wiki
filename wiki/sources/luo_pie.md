---
tags: [source]
date: 2026-05-26
sources: 1
---

# Luo PIE Source

> Source: `raw/pdfs/Luo_PIE.pdf`
> Paper: PIE: Parkour with Implicit-Explicit Learning Framework for Legged Robots, IEEE RA-L 2024

## Summary

This paper studies how a low-cost quadruped can perform parkour-style traversal on challenging terrain without depending on heavy pre-trained terrain-reconstruction modules.

For this vault, it matters because it gives the quadruped branch a more explicit `implicit plus explicit estimation` answer to the parkour problem, rather than treating agile traversal as only raw end-to-end policy learning.

## Method

The training backbone is [[reinforcement_learning]].

The paper centers on [[pie]], a one-stage end-to-end parkour framework for legged robots that uses dual-level implicit-explicit estimation.

For this vault, the important point is that PIE tries to preserve agility without assuming perfect perception or sacrificing too much performance margin for safety.

## Evaluation

The public record reports zero-shot real-world deployment on a low-cost quadruped with an unreliable egocentric depth camera and strong parkour performance on harsh terrain.

The broader takeaway is that quadruped parkour can be organized as a perception-aware but still compact end-to-end learning problem rather than only as a large explicit terrain-modeling stack.

## Notes / Critique

The strongest contribution is the systems balance: PIE tries to keep the policy simple enough to remain end-to-end while still acknowledging that both robot-state understanding and terrain understanding matter under noisy sensing.

That makes it a good bridge between:

- [[robot_parkour_learning]], which emphasizes broad multi-skill parkour under one policy,
- [[learning_robust_perceptive_locomotion_for_quadrupedal_robots_in_the_wild]], which emphasizes robust perception-aware locomotion,
- and [[perceptive_locomotion_through_nonlinear_model_predictive_control]], which represents the more explicit model-based alternative.

## Pages Created From This Source

- [[pie_parkour_with_implicit_explicit_learning_framework_for_legged_robots]]
- [[pie]]
