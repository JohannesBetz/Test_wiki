---
tags: [paper]
date: 2026-05-07
task: autonomous_racing
venue: "arXiv"
sources: 1
year: "2025"
eprint: "2502.03454"
url: "https://arxiv.org/abs/2502.03454"
topic:
  - autonomous_racing
  - minimum_time_planning
  - autonomous_racing_planning
  - autonomous_racing_control
tech_backbone: [model_predictive_control]
tech_representation: [g_g_g_v_diagrams]
tech_generation: [kineto_dynamical_planning]
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
simulators_used: []
---

# Kineto-Dynamical Planning and Accurate Execution of Minimum-Time Maneuvers on Three-Dimensional Circuits

> Kineto-Dynamical Planning and Accurate Execution of Minimum-Time Maneuvers on Three-Dimensional Circuits | arXiv:2502.03454 | Piccinini, Taddei, Betz, and Biral

## Summary

This paper proposes [[kineto_dynamical_planning]], an online minimum-time planning framework for autonomous racing on nonplanar tracks. The key idea is to use a learned kineto-dynamical vehicle model that is expressive enough to capture lateral-velocity and 3D road effects, yet efficient enough for repeated economic NMPC replanning.

The work targets a practical gap in 3D autonomous racing. Point-mass planners can be fast, but they may overestimate feasible performance and produce trajectories that look optimal offline yet fail during execution. Full high-fidelity optimal-control models are accurate, but they are too expensive for repeated online replanning. This paper aims for the middle ground.

## Method

The planner uses curvilinear coordinates on a 3D ribbon-road model with slope, banking, and curvature terms. Its state includes yaw rate, lateral velocity, longitudinal velocity, longitudinal acceleration, track progress, lateral offset, and relative yaw angle.

The learned vehicle model has three main parts:

- First-order yaw-rate dynamics scaled by a learned maximum yaw-rate envelope.
- First-order lateral-velocity dynamics parameterized as a shallow polynomial model of lateral, longitudinal, and vertical acceleration effects.
- 3D-aware longitudinal and lateral acceleration limits expressed through learned G-G-V-style constraints.

These constraints shift with gravity terms from slope and banking and expand or contract with a learned vertical-acceleration correction factor. The model is solved inside an economic NMPC planner that directly minimizes maneuver time subject to track and dynamic-feasibility constraints.

Learning happens over five rounds. Early rounds estimate rough performance envelopes and train low-level controllers. Later rounds refine the dynamic model and 3D performance terms from closed-loop telemetry. The final round specifically tunes the vertical-acceleration scaling term with Nelder-Mead because that parameter strongly affects lap time and is hard to identify conservatively from only feasible trajectories.

## Key Results

On the 3D Mugello circuit, the artificial race driver reaches a lap time of 115.322 s after learning, versus 114.598 s for the offline minimum-lap-time solution based on the same high-fidelity simulator. The final gap is 0.724 s over a 5.245 km lap.

The offline minimum-lap-time solution using the paper's own kineto-dynamical model is 114.388 s, only about 0.21 s from the simulator-based optimum. This suggests the planning model is close to the simulator's actual dynamics despite being much cheaper to optimize online.

Compared with the 3D point-mass benchmark from Rowold et al., the proposed method is better in closed loop. The benchmark appears faster offline because it overestimates the feasible acceleration envelope, but once executed online it laps in 116.110 s, which is 0.788 s slower than the proposed system.

The paper also shows the value of true 3D geometry. On an artificial 2D Mugello version, the learned driver laps in 118.839 s, while on the real 3D track it improves to 115.322 s by exploiting banking and slope for additional cornering and braking performance.

## Related Work

This paper is a direct successor to [[real_time_optimal_control_of_an_autonomous_rc_car_with_minimum_time]], extending kineto-dynamical planning from an RC-car setting to 3D race tracks and a more complete online learning-and-execution loop.

It also connects strongly to [[g_g_g_v_diagrams]]. Unlike quasi-steady-state approaches that compute high-fidelity envelopes offline, this paper learns 3D-aware acceleration constraints while driving and embeds them into online economic NMPC.

Compared with [[online_velocity_profile_generation_and_tracking_for_sampling_based_local_planning_algorithms_in_autonomous_racing_environments]], this work replans the trajectory itself rather than only updating speed on a fixed path. Compared with [[a_multi_stage_time_variant_motion_planner_for_agile_autonomous_driving_maneuvers]], it focuses on single-vehicle minimum-time execution rather than multi-agent maneuver trees.

## Notes / Critique

The best part of the paper is the closed-loop evaluation against a simulator-based minimum-lap-time optimum. That makes the performance claim much stronger than an offline-only planning paper.

A likely limitation is generalization. The learning loop depends on repeated laps, track-specific telemetry, and carefully chosen model structure. It is less clear how quickly the approach would adapt to tire changes, new tracks, or dynamic obstacle scenarios without extra machinery.
