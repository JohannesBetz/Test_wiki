---
tags: [technique]
date: 2026-05-07
sources: 4
---

# GripMap

## Definition

GripMap is a spatially resolved constraint map for autonomous racing. It stores local vehicle-dynamics scaling factors in a Frenet-frame grid so planning algorithms can adapt acceleration limits to track position.

In its demonstrated form, GripMap scales baseline [[g_g_g_v_diagrams]] with a local factor `theta_ij`, allowing planners to use higher acceleration where grip and software control are reliable and lower acceleration where dust, debris, rain, track position, or control limitations reduce usable dynamic potential.

[[accelerating_autonomy_insights_from_pro_racers_in_the_era_of_autonomous_racing]] motivates this distinction from the human side: professional drivers separate the vehicle limit from the driver limit, and the usable limit depends on what the driver or software can reliably control in that location and condition.

[[challenging_f1_drivers_in_physical_race_cars_with_human_inspired_online_learning]] uses the GripMap representation as the spatial performance map inside [[apex]], updating `theta(s,n)` online from observer and predictor signals.

[[online_velocity_profile_generation_and_tracking_for_sampling_based_local_planning_algorithms_in_autonomous_racing_environments]] shows how local scaling of dynamic constraints can be consumed by an online velocity planner.

## Why It Matters

Global vehicle models force a planner to choose between being too aggressive in low-grip regions or too conservative everywhere. GripMap gives [[autonomous_racing_planning]] a middle ground: it preserves local caution where needed while keeping performance elsewhere.

This matters especially for multi-vehicle racing. Overtaking and defending often push the ego vehicle away from the rubbered-in racing line, where grip may be lower and less well characterized.

## Implementation Pattern

[[gripmap_an_efficient_spatially_resolved_constraint_framework_for_offline_and_online_trajectory_planning_in_autonomous_racing]] implements GripMap as a dense Frenet-frame lookup table:

- `s`: longitudinal position along the track reference line.
- `n`: lateral offset from the reference line.
- `theta_ij`: local scaling factor for acceleration constraints.

The paper uses direct index computation from `(s, n)` into the lookup matrix, giving constant-time access. In online planning, the map is queried for each discretized point along sampled candidate trajectories.

## Representative Papers

- [[gripmap_an_efficient_spatially_resolved_constraint_framework_for_offline_and_online_trajectory_planning_in_autonomous_racing]]
- [[accelerating_autonomy_insights_from_pro_racers_in_the_era_of_autonomous_racing]]
- [[challenging_f1_drivers_in_physical_race_cars_with_human_inspired_online_learning]]
- [[online_velocity_profile_generation_and_tracking_for_sampling_based_local_planning_algorithms_in_autonomous_racing_environments]]

## Open Problems

The main open problem is map identification. A useful GripMap needs enough data to distinguish physical friction limits from software-driver limits, extrapolate away from the raceline, and adapt to changing track and tire conditions. The current static version is a strong integration layer, but online learning or self-identification would make it much more powerful.
