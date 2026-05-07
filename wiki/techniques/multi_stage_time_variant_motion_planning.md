---
tags: [technique]
date: 2026-05-07
sources: 1
---

# Multi-Stage Time-Variant Motion Planning

## Definition

Multi-stage time-variant motion planning is a sampling-based local planning strategy that builds maneuvers by concatenating trajectory stages with different time horizons.

In autonomous racing, it gives a planner both short-horizon agility for evasive movement and longer-horizon foresight for braking, overtaking, and returning to the raceline.

## Key Approach

[[a_multi_stage_time_variant_motion_planner_for_agile_autonomous_driving_maneuvers]] implements this with:

- Jerk-optimal polynomial trajectory primitives.
- A curvilinear track frame around an offline raceline.
- Multiple planning stages whose partial horizons sum to a fixed total horizon.
- Feasibility checks for curvature, speed, track bounds, and [[g_g_g_v_diagrams]].
- Cost-based pruning and other complexity reduction strategies.

## Relationship to Online Velocity Planning

[[online_velocity_profile_generation]] adapts the velocity profile along a fixed path. Multi-stage time-variant motion planning instead generates local maneuvers around dynamic agents, including rapid lateral motion and overtaking.

## Representative Papers

- [[a_multi_stage_time_variant_motion_planner_for_agile_autonomous_driving_maneuvers]]

## Open Problems

The main open problem is informed sampling. Future planners should use opponent predictions and tactical context to choose promising lateral and longitudinal end states instead of sampling many low-value candidates.
