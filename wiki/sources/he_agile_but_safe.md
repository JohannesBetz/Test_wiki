---
tags: [source]
date: 2026-05-22
sources: 1
---

# He Agile But Safe Source

> Source: `raw/pdfs/HE_Agile_But_Safe.pdf`
> Paper: Agile But Safe: Learning Collision-Free High-Speed Legged Locomotion, RSS 2024

## Summary

This paper studies how a quadruped can remain fast in cluttered environments without treating safety as something bolted on after the agile controller has already been trained.

For this vault, the paper matters because it gives the quadruped branch a stronger answer to the recurring question of how high-performance learned locomotion can remain collision-aware under deployment pressure.

## Method

The training backbone is [[reinforcement_learning]].

From the proceedings record and abstract support, the system combines:

- an agile locomotion policy,
- a dedicated recovery policy,
- and a learned control-theoretic reach-avoid value network that decides when to switch between them.

For this vault, the important point is structural: the framework does not ask one policy to be both maximally aggressive and maximally safe at every moment. Instead, it uses a learned safety estimator to govern when recovery should take over.

## Evaluation

The public record reports agile and collision-free locomotion on a physical quadruped in cluttered environments with fully onboard computation and sensing.

For this vault, the useful takeaway is broader than one benchmark:

safe high-speed locomotion may depend not only on better reward shaping, but on explicit online mechanisms that decide when aggressive behavior has become too risky to continue unchanged.

## Notes / Critique

The strongest contribution is the closed-loop coupling between agility and recovery through a learned reach-avoid safety signal.

That makes it a strong complement to:

- [[rapid_locomotion_via_reinforcement_learning]], which emphasizes raw agile learned locomotion,
- [[rma_rapid_motor_adaptation_for_legged_robots]], which emphasizes online adaptation to hidden conditions,
- and [[learning_robust_perceptive_locomotion_for_quadrupedal_robots_in_the_wild]], which emphasizes perceptive robustness under sensing uncertainty.

## Pages Created From This Source

- [[agile_but_safe_learning_collision_free_high_speed_legged_locomotion]]
- [[agile_but_safe_locomotion]]
