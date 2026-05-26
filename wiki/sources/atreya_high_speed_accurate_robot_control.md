---
tags: [source]
date: 2026-05-13
sources: 1
---

# Atreya High-Speed Accurate Robot Control Source

> Source: `raw/pdfs/Atreya_High-Speed_Accurate_Robot_Control_using_Learned_Forward_Kinodynamics_and_Non-linear_Least_Squares_Optimization.pdf`
> Paper: High-Speed Accurate Robot Control using Learned Forward Kinodynamics and Non-linear Least Squares Optimization, IROS 2022

## Summary

This paper studies high-speed control for mobile robots when simple kinematic or low-order models stop being accurate enough. At those speeds, slip, deformation, and other kinodynamic effects become too important to ignore.

For this vault, the paper matters because it offers a structured learned-control alternative to hand-derived high-speed models. Rather than learning an inverse kinodynamic controller tied to one narrow task, it learns a forward kinodynamic model and embeds it inside an online optimizer.

## Method

The paper proposes `Optim-FKD`, a formulation that combines a learned forward kinodynamic (`FKD`) model with non-linear least squares optimization.

That design is important because it broadens reuse. Earlier inverse-kinodynamics approaches can work well for a specific precomputed trajectory-following problem, but they tend to require retraining when the control objective changes. A learned forward model plus online optimization is more modular: different control objectives can be expressed as least-squares problems without relearning the dynamics model each time.

## Evaluation

The paper demonstrates the method on a scale 1:10 autonomous car at high speed.

For this vault, the key result is that the method improves trajectory tracking and optimal-control quality over baselines while remaining general enough to support multiple task objectives such as path following and time-optimal control.

## Notes / Critique

The strongest contribution is architectural. This is not just another learned vehicle model; it is a proposal for how to make learned high-speed dynamics reusable across multiple online control tasks.

It also connects naturally to [[f1tenth]] and to the broader [[Highly_dynamic_autonomous_system|highly dynamic autonomy]] branch, even though it is not a racing paper in the narrow competition sense.

## Pages Created From This Source

- [[high_speed_accurate_robot_control_using_learned_forward_kinodynamics_and_non_linear_least_squares_optimization]]
- [[learned_forward_kinodynamics]]
