---
tags: [source]
date: 2026-05-26
sources: 1
---

# Wu Adversarial Motion Priors Source

> Source: `raw/pdfs/Learning_Robust_and_Agile_Legged_Locomotion_Using_Adversarial_Motion_Priors.pdf`
> Paper: Learning Robust and Agile Legged Locomotion Using Adversarial Motion Priors, IEEE RA-L 2023

## Summary

This paper studies how a legged robot can learn agile locomotion that is not only task-successful but also shaped by a stronger prior over what natural, coordinated motion should look like.

For this vault, the paper matters because it gives the quadruped branch a motion-prior-driven learning story rather than only reward engineering, terrain perception, or explicit adaptation.

## Method

The training backbone is [[reinforcement_learning]].

The central idea is [[adversarial_motion_priors]].

From the paper title, venue record, and citation context, the framework uses an adversarially learned motion prior to guide locomotion learning toward more coordinated and agile behaviors.

For this vault, the important point is structural: instead of relying only on task rewards to discover good gaits, the policy is trained under an additional learned prior that biases behavior toward desirable motion structure.

## Evaluation

The available public metadata supports the main claim that adversarial motion priors improve robustness and agility in learned legged locomotion.

For this vault, the useful takeaway is broader than one reported result:

motion quality itself can become a learnable ingredient of locomotion, not only a side effect of reward optimization.

## Notes / Critique

The strongest contribution is the shift in what is treated as prior knowledge. Rather than hand-designing every desirable locomotion detail, the method tries to encode motion regularity through an adversarial prior.

That makes it a strong complement to:

- [[rapid_locomotion_via_reinforcement_learning]], which emphasizes curriculum-shaped agile locomotion,
- [[rma_rapid_motor_adaptation_for_legged_robots]], which emphasizes online latent adaptation,
- and [[agile_but_safe_learning_collision_free_high_speed_legged_locomotion]], which emphasizes safety-aware policy orchestration.

## Pages Created From This Source

- [[learning_robust_and_agile_legged_locomotion_using_adversarial_motion_priors]]
- [[adversarial_motion_priors]]
