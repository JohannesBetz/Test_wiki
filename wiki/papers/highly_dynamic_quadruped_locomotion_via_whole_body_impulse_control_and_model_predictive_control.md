---
tags: [paper]
date: 2026-05-22
task: robotics
venue: "arXiv"
sources: 1
year: "2019"
doi: "10.48550/arXiv.1909.06586"
url: "https://doi.org/10.48550/arXiv.1909.06586"
topic:
  - Highly_dynamic_autonomous_system
  - quadrupedal_locomotion
tech_backbone: [model_predictive_control]
tech_representation: []
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
hardware_used: [quadrupeds]
simulators_used: []
---

# Highly Dynamic Quadruped Locomotion via Whole-Body Impulse Control and Model Predictive Control

> Highly Dynamic Quadruped Locomotion via Whole-Body Impulse Control and Model Predictive Control | arXiv 2019 | Donghyun Kim, Jared Di Carlo, Benjamin Katz, Gerardo Bledt, and Sangbae Kim | DOI: 10.48550/arXiv.1909.06586

## Summary

This paper asks how a quadruped can achieve genuinely dynamic locomotion with aerial phases, rapid stance changes, and fast leg motion without collapsing into instability.

Its answer is a hybrid control architecture that combines [[model_predictive_control]] with a whole-body impulse-control layer on the Mini Cheetah platform.

## Method

An MPC layer computes a longer-horizon reaction-force profile using a simplified model of the robot. A whole-body controller then converts those force plans into joint torque, position, and velocity commands.

The key design choice is that the controller is organized around reaction-force realization rather than only around body-trajectory tracking.

That matters because highly dynamic quadruped locomotion often fails not because the desired motion is wrong in principle, but because the control stack cannot realize the required contact forces quickly and robustly enough once contacts become brief and aggressive.

## Key Results

The paper reports dynamic locomotion across multiple gait types and environments, including outdoor settings and treadmill experiments, with a top speed around `3.7 m/s`.

For this vault, the important result is broader than the number:

**highly dynamic quadruped behavior can already be achieved with explicit predictive control and whole-body force-centric control, not only with learned end-to-end locomotion policies.**

## Hardware Used

- [[quadrupeds]]


## Related Work

This paper belongs directly near [[quadrupedal_locomotion]], where it provides the most control-centric anchor among the current quadruped entries.

Compared with [[rapid_locomotion_via_reinforcement_learning]], the contrast is especially useful:

- Margolis shows what structured RL plus sim-to-real transfer can do for rapid quadruped locomotion,
- this paper shows what explicit MPC plus whole-body impulse control can do.

Compared with [[high_speed_control_and_navigation_for_quadrupedal_robots_on_complex_and_discrete_terrain]], this paper focuses more on dynamic gait execution itself than on the later problem of tightly coupling locomotion with navigation over complex discrete terrain.

It also belongs naturally near [[Highly_dynamic_autonomous_system]], because it reinforces a central vault theme: extreme embodied performance can come from different architectural families, and those families should be compared seriously rather than collapsed into one story about learning.

## Notes / Critique

The strongest contribution is the force-centric decomposition. It is a crisp example of how to split a difficult legged-locomotion problem into predictive force planning plus an executable whole-body layer.

Its limitation, from the vault's present perspective, is that it represents one point in the design space rather than the whole answer. Later RL locomotion work suggests that some agility and adaptability may emerge more naturally from structured experience-driven policies than from hand-designed controller stacks alone. That makes this paper especially valuable as a baseline and comparison point.
