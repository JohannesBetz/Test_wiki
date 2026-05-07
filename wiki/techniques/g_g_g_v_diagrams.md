---
tags: [technique]
date: 2026-05-07
sources: 4
---

# G-G-G-V Diagrams

## Definition

G-G-G-V diagrams are acceleration-envelope maps that describe feasible combinations of longitudinal acceleration, lateral acceleration, vertical acceleration, and vehicle speed.

They generalize classical G-G diagrams, which show longitudinal versus lateral acceleration limits, and G-G-V diagrams, which additionally account for speed-dependent effects such as aerodynamic drag and downforce. The extra vertical-acceleration dimension is useful for non-planar race tracks with crests, dips, banking, and changing normal load.

## Why It Matters

In [[autonomous_vehicle_racing]], planners and controllers often need dynamic constraints that are simple enough for real-time optimization but faithful enough to represent near-limit handling. A G-G-G-V diagram can act as a compact feasibility map for:

- [[autonomous_racing_planning]] and minimum-time trajectory generation.
- [[autonomous_racing_control]] near tire-force limits.
- [[model_predictive_control]] constraints.
- 3D track planning where vertical acceleration changes available tire force.

## Generation Methods

[[a_quasi_steady_state_black_box_simulation_approach_for_the_generation_of_g_g_g_v_diagrams]] generates these diagrams with [[quasi_steady_state_vehicle_simulation]]. Instead of deriving a differentiable vehicle model for an optimizer, it samples the acceleration envelope directly from forward simulation using virtual inertial forces and adaptive ramp-steer tests.

[[gripmap_an_efficient_spatially_resolved_constraint_framework_for_offline_and_online_trajectory_planning_in_autonomous_racing]] uses G-G-G-V constraints as the baseline acceleration envelope and then scales them locally through [[gripmap]] to account for spatially varying grip and software limits.

[[challenging_f1_drivers_in_physical_race_cars_with_human_inspired_online_learning]] uses a G-G-G-V point-mass model as the fixed experience-layer reference model for [[apex]].

[[online_velocity_profile_generation_and_tracking_for_sampling_based_local_planning_algorithms_in_autonomous_racing_environments]] uses related G-G-style constraints to compute online feasible velocity profiles over a three-dimensional raceline.

Earlier G-G-diagram-aware methods, such as [[path_tracking_for_autonomous_race_car_based_on_g_g_diagram]], use acceleration envelopes as control constraints but do not necessarily solve the problem of generating high-fidelity speed- and vertical-load-dependent envelopes.

## Representative Papers

- [[a_quasi_steady_state_black_box_simulation_approach_for_the_generation_of_g_g_g_v_diagrams]]
- [[gripmap_an_efficient_spatially_resolved_constraint_framework_for_offline_and_online_trajectory_planning_in_autonomous_racing]]
- [[challenging_f1_drivers_in_physical_race_cars_with_human_inspired_online_learning]]
- [[online_velocity_profile_generation_and_tracking_for_sampling_based_local_planning_algorithms_in_autonomous_racing_environments]]
- [[path_tracking_for_autonomous_race_car_based_on_g_g_diagram]]

## Open Problems

Key open issues include validating diagrams against real vehicle data, adapting diagrams online to tire wear and changing friction, efficiently sampling the high-dimensional envelope, and deciding how conservative the envelope should be when used inside real-time planners.
