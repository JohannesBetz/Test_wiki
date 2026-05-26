---
tags: [paper]
date: 2026-05-13
task: robotics
venue: "IEEE Robotics and Automation Letters 2023"
sources: 1
year: "2023"
doi: "10.1109/LRA.2023.3318190"
topic:
  - Highly_dynamic_autonomous_system
  - control
  - mobile_robotics
tech_backbone: []
tech_representation: [model_predictive_path_integral_control]
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
hardware_used: [cars_and_race_cars]
simulators_used: []
---

# Learning Terrain-Aware Kinodynamic Model for Autonomous Off-Road Rally Driving With Model Predictive Path Integral Control

> Learning Terrain-Aware Kinodynamic Model for Autonomous Off-Road Rally Driving With Model Predictive Path Integral Control | IEEE Robotics and Automation Letters 2023 | Hojin Lee, Taekyung Kim, Jungwi Mun, and Wonsuk Lee

## Summary

This paper asks how autonomous rally driving can remain aggressive and accurate when the terrain itself changes the vehicle dynamics.

Its answer is to learn a terrain-aware kinodynamic model and use that model inside [[model_predictive_path_integral_control]], so the controller can react online to terrain-dependent behavior rather than relying on one fixed dynamics approximation.

## Method

The paper combines two components:

- a learned kinodynamic model that is explicitly terrain-aware,
- and an MPPI controller that optimizes actions through stochastic trajectory sampling.

That pairing makes sense for off-road rally driving. Terrain variation can invalidate simplified dynamics models, while aggressive control at speed still demands online replanning under nonlinearity and uncertainty.

By learning the terrain-conditioned dynamics and placing them inside MPPI, the method keeps the control loop expressive without requiring a fully hand-derived terrain model or a purely end-to-end learned policy.

## Key Results

For this vault, the most important result is structural: the paper demonstrates a credible way to connect terrain-dependent learned dynamics with aggressive receding-horizon control for off-road rally driving.

It therefore strengthens the idea that high-speed control in unstructured environments depends not only on better optimization, but also on whether the model reflects what the current surface is doing to the vehicle.

## Hardware Used

- [[cars_and_race_cars]]


## Related Work

This paper belongs near [[model_predictive_path_integral_control]], where it reads as a learned-model extension of aggressive sampling-based control.

It also connects directly to [[high_speed_cornering_for_autonomous_off_road_rally_racing]] and [[real_time_trail_braking_maneuver_generation_for_off_road_vehicle_racing]], which represent earlier off-road rally control problems with more classical formulations.

Compared with [[aggressive_driving_with_model_predictive_path_integral_control]], the overlap is the use of MPPI for aggressive driving. The difference is that this paper pushes harder on terrain-conditioned modeling rather than only on the control method itself.

Compared with [[high_speed_accurate_robot_control_using_learned_forward_kinodynamics_and_non_linear_least_squares_optimization]], the overlap is learned high-speed dynamics for control. The difference is that this paper keeps stochastic sampling-based MPC in the loop, while the Atreya paper uses nonlinear least-squares optimization around a learned forward kinodynamic model.

## Notes / Critique

The strongest contribution is the refusal to separate modeling and control. Off-road rally performance depends on the terrain-sensitive dynamics being represented where the controller can actually use them.

For the vault, this makes the paper a good bridge between aggressive autonomous driving, learned vehicle modeling, and robust control under environment-dependent dynamics.
