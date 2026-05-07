---
tags: [topic]
date: 2026-05-06
sources: 7
---

# Autonomous Racing Control

## Definition

Autonomous racing control turns a reference trajectory into steering, throttle, and braking commands while minimizing lateral error, heading error, and velocity error near the limits of tire and vehicle stability.

## Key Approaches

[[autonomous_vehicles_on_the_edge]] groups control into:

- Classical control: lookahead control, feedforward/feedback steering, G-G-diagram-aware controllers, slip-angle-based control, torque vectoring, and nonlinear longitudinal control.
- [[model_predictive_control]]: MPPI, SRMPC, NMPC, LPV-MPC, tube MPC, envelope control, and mixed-integer formulations.
- Learning-based control: iterative learning control, learning MPC, Gaussian-process model-error learning, adaptive MPC, DNN-assisted control, and online scaling/correction.
- Drifting control: controllers for stable operation beyond normal handling limits at high sideslip angles.

[[learn_consolidate_dominate_orchestrating_cognitive_skill_distillation_and_alternating_learning_for_autonomous_racing]] contributes a learned high-level policy that generates path/velocity modifications while a lower-level NMPC controller handles trajectory tracking under vehicle constraints.

[[a_quasi_steady_state_black_box_simulation_approach_for_the_generation_of_g_g_g_v_diagrams]] strengthens the G-G-diagram-aware control thread by showing how to generate speed- and vertical-load-dependent acceleration envelopes from black-box vehicle simulation. These envelopes can constrain at-limit controllers without requiring the controller to carry a full high-fidelity vehicle model.

[[gripmap_an_efficient_spatially_resolved_constraint_framework_for_offline_and_online_trajectory_planning_in_autonomous_racing]] adds the spatial dimension: local grip and local software limitations can scale those envelopes differently across the track, reducing the chance that a controller is asked to track an infeasible trajectory in a dusty or poorly characterized region.

[[accelerating_autonomy_insights_from_pro_racers_in_the_era_of_autonomous_racing]] frames at-limit control as a stability-prioritization problem. Expert drivers coordinate steering, braking, throttle, and load transfer to manage understeer and oversteer, implying that autonomous controllers need situation-aware tradeoffs between stability, path tracking, speed tracking, and track limits.

[[challenging_f1_drivers_in_physical_race_cars_with_human_inspired_online_learning]] links online performance-envelope learning to control stress indicators, using ESC, TC, ABS, velocity error, lateral acceleration error, and lateral deviation as feedback for [[apex]].

[[spatially_aware_adaptive_trajectory_optimization_with_controller_guided_feedback_for_autonomous_racing]] uses MPC tracking error as planner feedback, making the controller an information source for global trajectory adaptation rather than only a tracking module.

## Representative Papers

- [[autonomous_vehicles_on_the_edge]]
- [[learn_consolidate_dominate_orchestrating_cognitive_skill_distillation_and_alternating_learning_for_autonomous_racing]]
- [[a_quasi_steady_state_black_box_simulation_approach_for_the_generation_of_g_g_g_v_diagrams]]
- [[gripmap_an_efficient_spatially_resolved_constraint_framework_for_offline_and_online_trajectory_planning_in_autonomous_racing]]
- [[accelerating_autonomy_insights_from_pro_racers_in_the_era_of_autonomous_racing]]
- [[challenging_f1_drivers_in_physical_race_cars_with_human_inspired_online_learning]]
- [[spatially_aware_adaptive_trajectory_optimization_with_controller_guided_feedback_for_autonomous_racing]]

## Open Problems

The central problems are high-accuracy path/heading/velocity tracking, stable behavior under high lateral and longitudinal acceleration, real-time nonlinear modeling, and control policies that adapt to changing tires, friction, aerodynamics, and track conditions.

The professional-driver perspective adds robust limit detection and recovery from limit understeer or limit oversteer as first-class control problems.
