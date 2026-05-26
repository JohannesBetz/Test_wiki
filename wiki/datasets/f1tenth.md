---
tags: [dataset]
date: 2026-05-06
sources: 3
---

# F1TENTH

## Definition

F1TENTH is a 1:10-scale autonomous racing platform and competition ecosystem used for research, education, and racing algorithm evaluation.

## Key Approaches

In [[autonomous_vehicles_on_the_edge]], F1TENTH vehicles are described as modified RC-scale cars with interchangeable sensors such as cameras, 2D LiDAR, IMU, indoor GPS, and wheel-speed sensors, often using Nvidia Jetson compute and ROS/ROS2 software.

[[spatially_aware_adaptive_trajectory_optimization_with_controller_guided_feedback_for_autonomous_racing]] uses F1TENTH hardware to validate adaptive constraint learning under different tire-friction configurations.

[[forzaeth_race_stack_scaled_autonomous_head_to_head_racing_on_fully_commercial_off_the_shelf_hardware]] adds a modern full-stack competition example: [[forzaeth_race_stack]] targets reproducible head-to-head racing on commercial off-the-shelf 1:10 hardware rather than only isolated module validation.

[[high_speed_accurate_robot_control_using_learned_forward_kinodynamics_and_non_linear_least_squares_optimization]] adds a control-modeling example: the same 1:10-scale car setting can be used not only for racing stacks, but also for learned high-speed kinodynamic control with reusable online optimization.

[[efficient_trajectory_optimization_for_autonomous_racing_via_formula_1_data_driven_initialization]] adds a transfer-from-expert-data example: the F1TENTH setting can also be used as a target platform for testing whether full-scale Formula 1 driving data helps initialize autonomous racing trajectory optimization more efficiently.

## Papers Using This

- [[autonomous_vehicles_on_the_edge]]
- [[spatially_aware_adaptive_trajectory_optimization_with_controller_guided_feedback_for_autonomous_racing]]
- [[forzaeth_race_stack_scaled_autonomous_head_to_head_racing_on_fully_commercial_off_the_shelf_hardware]]
- [[high_speed_accurate_robot_control_using_learned_forward_kinodynamics_and_non_linear_least_squares_optimization]]
- [[efficient_trajectory_optimization_for_autonomous_racing_via_formula_1_data_driven_initialization]]

## Notes

This page is placed under datasets because the current schema does not define a dedicated `platforms/` directory. It should be split or moved if the wiki later introduces first-class platform pages.
