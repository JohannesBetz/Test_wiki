---
tags: [technique]
date: 2026-05-13
sources: 1
---

# Model Predictive Path Integral Control

## Definition

Model predictive path integral control (`MPPI`) is a sampling-based receding-horizon control method that optimizes behavior by evaluating many stochastic trajectory rollouts under a dynamics model and reweighting them according to cost.

## Key Approach

[[learning_terrain_aware_kinodynamic_model_for_autonomous_off_road_rally_driving_with_model_predictive_path_integral_control]] applies MPPI to autonomous off-road rally driving with a learned terrain-aware kinodynamic model.

The appeal of MPPI is that it can handle aggressive nonlinear driving behavior without requiring the optimizer to depend entirely on smooth local approximations. That makes it attractive for rally driving, aggressive autonomous driving, and other high-speed settings with complex dynamics.

When paired with a learned model, MPPI can also absorb environment-dependent effects such as terrain changes more naturally than a controller built around one fixed nominal model.

## Relationship to High-Speed Control

This technique belongs near [[model_predictive_control]] and [[Highly_dynamic_autonomous_system]].

Compared with classical deterministic MPC, MPPI is more explicitly sampling-based and often more comfortable with highly nonlinear, aggressive control problems. Compared with end-to-end learned policies, it keeps an online optimization layer that can still adapt behavior at deployment time.

## Representative Papers

- [[aggressive_driving_with_model_predictive_path_integral_control]]
- [[robust_model_predictive_path_integral_control_analysis_and_performance_guarantees]]
- [[learning_terrain_aware_kinodynamic_model_for_autonomous_off_road_rally_driving_with_model_predictive_path_integral_control]]

## Open Problems

Open problems include model quality under rapid environment change, runtime scaling with richer action spaces and longer horizons, robustness to distribution shift in the learned dynamics model, and how MPPI should trade nominal speed against safety under severe uncertainty.
