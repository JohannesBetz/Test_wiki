---
tags: [topic]
date: 2026-05-06
sources: 11
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

[[spatially_aware_adaptive_trajectory_optimization_with_controller_guided_feedback_for_autonomous_racing]] takes a trajectory-centric view: MPC tracking errors update a spatial constraint map, and CMA-ES reoptimizes a NURBS raceline and timing over repeated laps.

[[a_multi_stage_time_variant_motion_planner_for_agile_autonomous_driving_maneuvers]] contributes a local multi-agent planning method: [[multi_stage_time_variant_motion_planning]] uses short first-stage horizons for agile avoidance and longer later stages for foresight and raceline recovery.

[[kineto_dynamical_planning_and_accurate_execution_of_minimum_time_maneuvers_on_three_dimensional_circuits]] adds a 3D minimum-time replanning perspective: [[kineto_dynamical_planning]] uses a learned reduced-order vehicle model plus economic NMPC to stay close to high-fidelity minimum-lap-time performance on banked and sloped circuits.

[[a_competitor_aware_race_management_policy_a_game_theoretical_approach]] pushes planning to the race-strategy level: [[competitor_aware_race_management]] uses a lower-level game-theoretic lap model and an upper-level RL policy to choose energy deployment, pit stops, and charging against a specific opponent over an entire electric endurance race.

## Representative Papers

- [[autonomous_vehicles_on_the_edge]]
- [[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]]
- [[learn_consolidate_dominate_orchestrating_cognitive_skill_distillation_and_alternating_learning_for_autonomous_racing]]
- [[a_quasi_steady_state_black_box_simulation_approach_for_the_generation_of_g_g_g_v_diagrams]]
- [[gripmap_an_efficient_spatially_resolved_constraint_framework_for_offline_and_online_trajectory_planning_in_autonomous_racing]]
- [[accelerating_autonomy_insights_from_pro_racers_in_the_era_of_autonomous_racing]]
- [[challenging_f1_drivers_in_physical_race_cars_with_human_inspired_online_learning]]
- [[online_velocity_profile_generation_and_tracking_for_sampling_based_local_planning_algorithms_in_autonomous_racing_environments]]
- [[spatially_aware_adaptive_trajectory_optimization_with_controller_guided_feedback_for_autonomous_racing]]
- [[a_multi_stage_time_variant_motion_planner_for_agile_autonomous_driving_maneuvers]]
- [[kineto_dynamical_planning_and_accurate_execution_of_minimum_time_maneuvers_on_three_dimensional_circuits]]
- [[a_competitor_aware_race_management_policy_a_game_theoretical_approach]]

## Open Problems

Major gaps include multi-vehicle planning at high speed, recursive feasibility under dynamic constraints, real-time replanning, non-convex collision avoidance, interaction with non-cooperative agents, and decision making under high uncertainty.

GT Sophy suggests that scenario design and opponent diversity can partly substitute for explicit behavior-planning rules, but long-horizon race strategy remains open.

GripMap adds a practical constraint-map problem: planners need local friction and software-limit estimates that are accurate enough away from the racing line, especially during overtaking.

Professional-driver interviews add another gap: planners should learn when to exploit curbs, track margins, and nonstandard lines from vehicle response rather than relying entirely on a predeclared drivable area.

Online velocity planning adds a fixed-path limitation: speed can adapt quickly along the raceline, but feasibility becomes harder when the local planner deviates laterally for overtaking or obstacle avoidance.

Multi-stage sampling adds a computational tradeoff: richer maneuver trees improve agility and robustness, but require strong pruning and eventually environment-aware sampling to stay real-time.

Kineto-dynamical planning adds a model-selection tradeoff: richer reduced-order models can close the gap to high-fidelity minimum-time solutions, but they also require more careful identification and may generalize less gracefully across tracks and conditions.

Competitor-aware race management adds a hierarchy tradeoff: strategic race-level policies can optimize energy and position over long horizons, but they depend on lower-level surrogate models of interaction that may break when the field grows beyond a few agents or when drafting assumptions shift.
