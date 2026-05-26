---
tags: [source]
date: 2026-05-22
sources: 1
---

# Grandia Perceptive Locomotion NMPC Source

> Source: `raw/pdfs/Grandia_Perceptive Locomotion_NMPC.pdf`
> Paper: Perceptive Locomotion Through Nonlinear Model-Predictive Control, IEEE Transactions on Robotics 2023

## Summary

This paper studies how a quadruped can use terrain perception inside a full online control pipeline without giving up the dynamic consistency and real-time structure of model-based control.

For this vault, the paper matters because it gives a control-centric answer to the same broad question raised by the newer perceptive-locomotion RL work: how can uncertain exteroceptive terrain information change what motions remain executable at speed?

## Method

The core idea is [[perceptive_nonlinear_model_predictive_control]].

The system combines:

- a robot-centric elevation-map representation of the terrain,
- local terrain abstractions such as steppability regions, plane segments, and a signed distance field,
- and an online nonlinear model-predictive controller that optimizes full-body motion while respecting terrain-feasibility constraints.

This makes the paper a useful bridge between [[perceptive_locomotion]] and [[model_predictive_control]].

## Evaluation

According to the publication record, the controller is validated in simulation and on the physical ANYmal quadruped across gaps, slopes, and stepping-stone-style terrain, with strong dynamic climbing and foothold-aware motion generation.

For this vault, the key result is architectural: perception is not merely fused into a learned policy, but turned into optimization constraints that shape motion online.

## Notes / Critique

The strongest contribution is that it shows perceptive locomotion can remain deeply model-based. The system does not have to choose between seeing the terrain and preserving a structured predictive controller.

That makes it a strong complement to:

- [[learning_robust_perceptive_locomotion_for_quadrupedal_robots_in_the_wild]], which emphasizes learned perception-action fusion,
- [[highly_dynamic_quadruped_locomotion_via_whole_body_impulse_control_and_model_predictive_control]], which emphasizes dynamic MPC without the same terrain-perception integration,
- and [[high_speed_control_and_navigation_for_quadrupedal_robots_on_complex_and_discrete_terrain]], which emphasizes tightly coupled terrain-aware mobility on complex foothold-like terrain.

## Pages Created From This Source

- [[perceptive_locomotion_through_nonlinear_model_predictive_control]]
- [[perceptive_nonlinear_model_predictive_control]]
