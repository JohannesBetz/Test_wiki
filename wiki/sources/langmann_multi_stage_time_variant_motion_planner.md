---
tags: [source]
date: 2026-05-07
sources: 1
---

# Langmann Multi-Stage Time-Variant Motion Planner Source

> Source: `raw/pdfs/Langmann_A_Multi-Stage_Time-Variant_Motion_Planner_for_Agile_Autonomous_Driving_Maneuvers.pdf`
> Paper: A Multi-Stage Time-Variant Motion Planner for Agile Autonomous Driving Maneuvers, IEEE Open Journal of Intelligent Transportation Systems, 2026

## Summary

This paper introduces [[multi_stage_time_variant_motion_planning]], a sampling-based local planning method for agile autonomous driving in dynamic multi-vehicle environments. The method builds a maneuver tree by concatenating trajectory segments with different time horizons, combining short-horizon lateral agility with longer-horizon foresight.

The paper is relevant to [[autonomous_racing_planning]] because it targets the gap between single-stage sampling planners, which can be agile but myopic, and graph or long-horizon planners, which can see farther but may be less flexible or computationally heavy.

## Method

The planner operates in a curvilinear track frame and uses an offline time-optimal raceline as reference. Candidate trajectories are generated as jerk-optimal polynomial primitives around the raceline profile and checked for curvature, velocity, track-boundary, and [[g_g_g_v_diagrams|G-G-G-V]] acceleration feasibility.

A planning step is split into multiple stages. Each stage has a partial time horizon, and valid partial trajectories from one stage become start states for the next. Different fixed horizon configurations preserve the total horizon while allowing both quick maneuvers and longer-term planning.

To keep the combinatorial tree tractable, the paper proposes complexity reduction strategies: limit the number of stages to two, reduce sample density in later stages, constrain final-stage samples toward the raceline, and expand only the lowest-cost first-stage trajectories.

## Evaluation

Experiments use simulated autonomous racing scenarios on Yas Marina Circuit, with the A2RL setting as motivation. The method is benchmarked against a single-stage sampling planner and a hybrid graph planner.

Key results include:

- Static obstacle avoidance: the multi-stage planner avoids a stationary obstacle at 40 m/s where the single-stage planner collides.
- Full-lap dynamic obstacles: with 13 opponent vehicles, the multi-stage planner completes the lap in 122.86 s versus 128.43 s for the single-stage planner and 135.57 s for the hybrid graph planner.
- Head-to-head overtaking in Turn 5: the multi-stage planner completes the evaluated maneuver 0.36 s faster than the single-stage planner and 2.24 s faster than the hybrid graph planner.
- Prediction-error robustness: with longitudinal and lateral opponent prediction errors, the multi-stage planner completes a full lap without collisions.
- Reactive opponents: over 100 runs, the multi-stage planner completes 93 overtakes with 2 collisions, outperforming the single-stage planner and hybrid graph planner.
- Closed-loop validation: high-fidelity closed-loop simulation shows the generated maneuvers can be tracked without collisions.

## Notes / Critique

The strongest contribution is the time-horizon structure: fixed discrete partial horizons give the planner kinematic diversity without making horizon length a continuous optimization variable.

The main limitation is uninformed sampling. The planner still generates many terminal states that are obviously poor or infeasible given opponent positions. The authors identify environment-aware heuristics as future work.

## Pages Created From This Source

- [[a_multi_stage_time_variant_motion_planner_for_agile_autonomous_driving_maneuvers]]
- [[multi_stage_time_variant_motion_planning]]
