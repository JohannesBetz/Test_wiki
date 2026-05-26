---
tags: [source]
date: 2026-05-22
sources: 1
---

# Kim Highly Dynamic Locomotion Quadruped Source

> Source: `raw/pdfs/Kim_HighlyDynamic_Locomotion_Quadruped.pdf`
> Paper: Highly Dynamic Quadruped Locomotion via Whole-Body Impulse Control and Model Predictive Control, arXiv 2019

## Summary

This paper studies how a quadrupedal robot can achieve highly dynamic locomotion with aerial phases, short stance times, and rapid contact transitions using an explicit control architecture rather than a purely learned policy.

For this vault, the paper matters because it is a strong control-centric anchor for the quadruped branch. It shows that highly dynamic embodied competence can emerge from predictive force planning and whole-body control, not only from experience-driven RL.

## Method

The controller combines:

- [[model_predictive_control]] over a simplified dynamics model to plan reaction forces,
- and a whole-body impulse-control layer that turns those force plans into executable joint commands.

The key conceptual point is force-centric control. Instead of asking the low-level controller mainly to track a body trajectory, the architecture emphasizes realizing the reaction forces needed for dynamic locomotion.

## Evaluation

The controller is tested on the Mini Cheetah quadruped across multiple gaits and environments, including outdoor operation and treadmill experiments.

For the purposes of this vault, the key takeaway is that the robot reportedly reaches about `3.7 m/s` while remaining versatile across several gait styles and terrain contexts.

## Notes / Critique

The strongest value of the paper is architectural clarity. It gives the wiki a clean explicit-control counterpart to the newer quadruped RL papers:

- [[rapid_locomotion_via_reinforcement_learning]] emphasizes structured RL plus sim-to-real transfer,
- [[high_speed_control_and_navigation_for_quadrupedal_robots_on_complex_and_discrete_terrain]] emphasizes tightly coupled high-speed control and navigation,
- this paper emphasizes MPC plus whole-body impulse control for dynamic gait execution itself.

## Pages Created From This Source

- [[highly_dynamic_quadruped_locomotion_via_whole_body_impulse_control_and_model_predictive_control]]
