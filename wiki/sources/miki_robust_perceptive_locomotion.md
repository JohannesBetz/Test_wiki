---
tags: [source]
date: 2026-05-22
sources: 1
---

# Miki Robust Perceptive Locomotion Source

> Source: `raw/pdfs/Miki_learning_Robust_perceptive_Locomotion.pdf`
> Paper: Learning robust perceptive locomotion for quadrupedal robots in the wild, Science Robotics 2022

## Summary

This paper studies whether a quadruped can use exteroceptive perception robustly enough to move quickly over real, messy terrain instead of relying only on proprioception and reactive contact correction.

For this vault, the paper matters because it turns perception into a direct ingredient of high-performance locomotion rather than a separate upstream module.

## Method

The core idea is robust [[perceptive_locomotion]].

The system combines:

- exteroceptive terrain information from a robot-centric elevation map,
- proprioceptive state information from the quadruped itself,
- an attention-based recurrent encoder that fuses both modalities,
- and a teacher-student training pipeline in which a privileged teacher is learned with [[reinforcement_learning]] and then distilled into a deployment-ready student policy.

This makes the paper a useful bridge across several wiki branches: high-speed perception, legged locomotion, RL, and sim-to-real deployment.

## Evaluation

According to the project page and article metadata, the controller is deployed zero-shot on physical ANYmal quadrupeds and tested across difficult natural and urban terrain, including unreliable or misleading depth perception, stairs, vegetation, slippery surfaces, and long-duration outdoor missions.

For this vault, the key result is not just robustness but systems integration: perception helps the robot move faster because it can anticipate terrain before contact.

## Notes / Critique

The strongest contribution is the fusion argument. The paper does not treat perception as an optional add-on, but as a control-relevant capability that has to survive missing data, reflective surfaces, pose drift, and other real field failures.

That makes it a strong complement to:

- [[rapid_locomotion_via_reinforcement_learning]], which emphasizes rapid learned locomotion,
- [[rma_rapid_motor_adaptation_for_legged_robots]], which emphasizes latent online adaptation,
- and [[high_speed_control_and_navigation_for_quadrupedal_robots_on_complex_and_discrete_terrain]], which emphasizes terrain-aware control and navigation design.

## Pages Created From This Source

- [[learning_robust_perceptive_locomotion_for_quadrupedal_robots_in_the_wild]]
- [[perceptive_locomotion]]
