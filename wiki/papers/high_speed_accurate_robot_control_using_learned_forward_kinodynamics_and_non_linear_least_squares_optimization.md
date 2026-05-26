---
tags: [paper]
date: 2026-05-13
task: robotics
venue: "2022 IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS)"
sources: 1
year: "2022"
doi: "10.1109/IROS47612.2022.9981259"
topic:
  - Highly_dynamic_autonomous_system
  - control
  - mobile_robotics
tech_backbone: []
tech_representation: [learned_forward_kinodynamics]
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: [f1tenth]
models_used: []
hardware_used: [cars_and_race_cars]
simulators_used: []
---

# High-Speed Accurate Robot Control using Learned Forward Kinodynamics and Non-linear Least Squares Optimization

> High-Speed Accurate Robot Control using Learned Forward Kinodynamics and Non-linear Least Squares Optimization | 2022 IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS) | Pranav Atreya, Haresh Karnan, Kavan Singh Sikand, Xuesu Xiao, Sadegh Rabiee, and Joydeep Biswas

## Summary

This paper asks how a robot can stay accurate at high speed when simplified kinematic assumptions stop being trustworthy.

Its answer is `Optim-FKD`: learn a forward kinodynamic model of the robot and use that model inside a non-linear least squares optimizer so the same learned dynamics can support multiple control objectives in real time.

## Method

The paper is motivated by a limitation in earlier learned inverse-kinodynamics approaches. If the controller learns a task-specific inverse mapping, it can work well for one narrow objective, but changing the control problem may require retraining a new model.

`Optim-FKD` changes the decomposition:

- learn a forward kinodynamic (`FKD`) model that predicts how controls evolve the robot state,
- then solve online control objectives as non-linear least squares problems using that learned model.

This matters because the control objective can change without replacing the learned dynamics model. Path following, time-optimal control, and other high-speed tasks can all be posed through the same optimization machinery.

## Key Results

The experiments use a scale 1:10 autonomous car and show that the approach can control the platform accurately at high speed while outperforming baselines.

For this vault, the most important result is the generality claim: learned high-speed dynamics are made reusable across several control problems, rather than being locked to one precomputed-trajectory-following setup.

## Hardware Used

- [[cars_and_race_cars]]


## Related Work

This paper pairs naturally with [[learning_inverse_kinodynamics_for_accurate_high_speed_off_road_navigation_on_unstructured]], which tackles a related high-speed modeling problem from the inverse-kinodynamics direction. The difference is the key point: that earlier line is more task-specific, while this paper is explicitly designed to broaden the range of objectives one learned model can support.

It also belongs near [[Highly_dynamic_autonomous_system]], where runtime accuracy and dynamic fidelity become first-class control constraints rather than implementation details.

Compared with [[real_time_neural_mpc_deep_learning_model_predictive_control_for_quadrotors_and_agile_robotic_platforms]], the overlap is agile control with learned structure, but the emphasis is different. Neural MPC distills a controller; this paper learns a forward dynamics model and keeps online optimization explicit.

## Notes / Critique

The strongest idea is the modularity argument. Forward learned kinodynamics plus online optimization is a cleaner abstraction boundary than retraining a new inverse controller every time the objective changes.

For the racing-adjacent parts of this vault, that makes the paper useful as a bridge from narrow high-speed controller learning toward more reusable learned-dynamics control stacks on small-scale cars.
