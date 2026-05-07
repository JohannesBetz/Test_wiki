---
tags: [topic]
date: 2026-05-06
sources: 8
---

# Autonomous Racing Planning

## Definition

Autonomous racing planning computes racelines, local trajectories, and high-level behavior for a racecar driving near its dynamic limits.

## Key Approaches

[[autonomous_vehicles_on_the_edge]] separates planning into three layers:

- Global planning: minimum-time, minimum-curvature, energy-aware, geometric, evolutionary, and optimal-control raceline generation.
- Local planning: obstacle avoidance and dynamic feasibility using MPC, graph search, splines, RRT variants, clothoids, sampled motion primitives, and stochastic prediction.
- Behavioral planning: overtaking, blocking, interaction, race-control response, and cost/game-theoretic selection among candidate maneuvers.

[[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]] gives a contrasting learned-policy approach: GT Sophy does not explicitly decompose racing into planning and control modules, but learns tactical behaviors such as passing, blocking, draft disruption, and emergency maneuvers from mixed scenarios.

[[learn_consolidate_dominate_orchestrating_cognitive_skill_distillation_and_alternating_learning_for_autonomous_racing]] uses a learned policy to modify an expert reference path and velocity profile, then relies on a lower-level NMPC tracker for feasible vehicle control.

[[a_quasi_steady_state_black_box_simulation_approach_for_the_generation_of_g_g_g_v_diagrams]] contributes a constraint-generation layer for planners: [[g_g_g_v_diagrams]] can summarize feasible acceleration limits over speed and vertical acceleration so minimum-time planners can use high-fidelity vehicle dynamics without embedding the full simulator in the online optimization.

[[gripmap_an_efficient_spatially_resolved_constraint_framework_for_offline_and_online_trajectory_planning_in_autonomous_racing]] makes those constraints spatially local through [[gripmap]], enabling offline raceline optimization and online sampling-based planning to account for track-position-dependent grip.

[[accelerating_autonomy_insights_from_pro_racers_in_the_era_of_autonomous_racing]] adds a human-expertise view: professional drivers progressively explore braking points, curbs, track boundaries, and racing-line variations, suggesting that autonomous planners need self-exploration mechanisms rather than only fixed offline racelines.

[[challenging_f1_drivers_in_physical_race_cars_with_human_inspired_online_learning]] implements this as [[apex]], which updates spatial performance-envelope constraints online and feeds them to an online velocity planner.

[[online_velocity_profile_generation_and_tracking_for_sampling_based_local_planning_algorithms_in_autonomous_racing_environments]] focuses on that online velocity planner: it adapts speed along a fixed 3D raceline to changing dynamic constraints and adds spatial-domain sampling so local trajectories respect apex and braking-point locations.

## Representative Papers

- [[autonomous_vehicles_on_the_edge]]
- [[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]]
- [[learn_consolidate_dominate_orchestrating_cognitive_skill_distillation_and_alternating_learning_for_autonomous_racing]]
- [[a_quasi_steady_state_black_box_simulation_approach_for_the_generation_of_g_g_g_v_diagrams]]
- [[gripmap_an_efficient_spatially_resolved_constraint_framework_for_offline_and_online_trajectory_planning_in_autonomous_racing]]
- [[accelerating_autonomy_insights_from_pro_racers_in_the_era_of_autonomous_racing]]
- [[challenging_f1_drivers_in_physical_race_cars_with_human_inspired_online_learning]]
- [[online_velocity_profile_generation_and_tracking_for_sampling_based_local_planning_algorithms_in_autonomous_racing_environments]]

## Open Problems

Major gaps include multi-vehicle planning at high speed, recursive feasibility under dynamic constraints, real-time replanning, non-convex collision avoidance, interaction with non-cooperative agents, and decision making under high uncertainty.

GT Sophy suggests that scenario design and opponent diversity can partly substitute for explicit behavior-planning rules, but long-horizon race strategy remains open.

GripMap adds a practical constraint-map problem: planners need local friction and software-limit estimates that are accurate enough away from the racing line, especially during overtaking.

Professional-driver interviews add another gap: planners should learn when to exploit curbs, track margins, and nonstandard lines from vehicle response rather than relying entirely on a predeclared drivable area.

Online velocity planning adds a fixed-path limitation: speed can adapt quickly along the raceline, but feasibility becomes harder when the local planner deviates laterally for overtaking or obstacle avoidance.
