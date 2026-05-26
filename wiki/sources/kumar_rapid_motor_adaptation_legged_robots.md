---
tags: [source]
date: 2026-05-22
sources: 1
---

# Kumar Rapid Motor Adaptation Legged Robots Source

> Source: `raw/pdfs/Kumar_Rapid Motor Adaptation for Legged Robots.pdf`
> Paper: RMA: Rapid Motor Adaptation for Legged Robots, RSS 2021

## Summary

This paper studies how a legged robot can adapt in real time to changing terrain, payload, and effective dynamics conditions without manual controller switching or retraining for every new regime.

For this vault, the paper matters because it is one of the clearest examples that fast embodied competence may require online latent adaptation, not only a strong fixed locomotion policy.

## Method

The core idea is `Rapid Motor Adaptation` or `RMA`.

The architecture combines:

- a base locomotion policy,
- and an adaptation module that infers a latent environment or dynamics variable from recent motion history.

This enables the robot to update its behavior in fractions of a second without explicit terrain labels or handcrafted mode-switching logic.

## Evaluation

According to the public record of the paper, the learned controller is deployed directly on the Unitree A1 quadruped without real-world fine-tuning and tested across a variety of difficult real terrains including rocky, slippery, deformable, grassy, sandy, and stair-like settings.

For this vault, the key result is not only locomotion quality but adaptation speed: the robot remains competent when hidden conditions change.

## Notes / Critique

The strongest contribution is architectural. This is not just another locomotion policy, but a concrete argument that adaptation itself can be learned as part of the control stack.

That makes the paper a strong complement to:

- [[rapid_locomotion_via_reinforcement_learning]], which emphasizes rapid learned locomotion,
- [[highly_dynamic_quadruped_locomotion_via_whole_body_impulse_control_and_model_predictive_control]], which emphasizes explicit predictive control,
- and [[high_speed_control_and_navigation_for_quadrupedal_robots_on_complex_and_discrete_terrain]], which emphasizes tightly coupled control and navigation.

## Pages Created From This Source

- [[rma_rapid_motor_adaptation_for_legged_robots]]
- [[rapid_motor_adaptation]]
