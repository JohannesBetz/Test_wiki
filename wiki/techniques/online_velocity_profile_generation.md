---
tags: [technique]
date: 2026-05-07
sources: 2
---

# Online Velocity Profile Generation

## Definition

Online velocity profile generation recomputes a feasible speed reference during runtime, usually along a fixed path or raceline, when vehicle-dynamics constraints change.

In autonomous racing, it is useful when the path remains valid but the speed profile must adapt to grip, tire temperature, power limits, vertical acceleration, or learned local performance-envelope changes.

## Key Approach

[[online_velocity_profile_generation_and_tracking_for_sampling_based_local_planning_algorithms_in_autonomous_racing_environments]] combines:

- Online apex detection over an upcoming track horizon.
- Forward-backward velocity-profile generation over raceline segments.
- G-G-style acceleration constraints with speed and apparent vertical acceleration.
- Spatial-domain sampling so local planner trajectories remain aligned with braking points and apexes.

This gives [[autonomous_racing_planning]] a way to keep an offline raceline path while adapting speed online.

## Relationship to APEX and GripMap

[[apex]] learns local performance scaling values and [[gripmap]] stores spatially varying constraints. Online velocity profile generation consumes those constraints and turns them into a velocity reference that can be tracked by a local planner.

[[multi_stage_time_variant_motion_planning]] is complementary: it focuses on local dynamic-agent maneuvers around the raceline, while online velocity profile generation focuses on adapting speed along the fixed raceline.

## Representative Papers

- [[online_velocity_profile_generation_and_tracking_for_sampling_based_local_planning_algorithms_in_autonomous_racing_environments]]
- [[a_multi_stage_time_variant_motion_planner_for_agile_autonomous_driving_maneuvers]]
- [[challenging_f1_drivers_in_physical_race_cars_with_human_inspired_online_learning]]

## Open Problems

The key open problems are feasibility for paths that deviate laterally from the raceline, transient vehicle dynamics, jerk regularization, and real-world validation under actuator and controller limits.
