---
tags: [paper]
date: 2026-05-07
task: autonomous_racing
venue: "IEEE Open Journal of Intelligent Transportation Systems"
sources: 1
year: "2026"
doi: "10.1109/OJITS.2026.3686916"
topic:
  - autonomous_racing
  - local_planning
  - sampling_based_planning
  - multi_vehicle_racing
tech_backbone: []
tech_representation: [g_g_g_v_diagrams]
tech_generation: [multi_stage_time_variant_motion_planning]
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: [abu_dhabi_autonomous_racing_league]
models_used: []
simulators_used: []
---

# A Multi-Stage Time-Variant Motion Planner for Agile Autonomous Driving Maneuvers

> A Multi-Stage Time-Variant Motion Planner for Agile Autonomous Driving Maneuvers | IEEE Open Journal of Intelligent Transportation Systems, 2026 | Langmann, Kohl, Ogretmen, Piccinini, and Betz | DOI: 10.1109/OJITS.2026.3686916

## Summary

This paper proposes [[multi_stage_time_variant_motion_planning]], a sampling-based local planner for agile autonomous driving maneuvers in dynamic racing environments. It concatenates multiple trajectory stages with different time horizons, producing a tree of candidate maneuvers that combines near-term lateral agility with longer-term foresight.

The work addresses a concrete local-planning limitation: single-stage sampling planners may react quickly only if their horizon is short, but short horizons hurt recursive feasibility and anticipation. Long horizons improve foresight, but reduce agility. The multi-stage formulation gives the first stage a short horizon for evasive movement and later stages longer horizons for recovery, braking, and raceline reintegration.

## Method

The planner uses a curvilinear track frame and a time-optimal raceline as reference. Trajectory primitives are generated analytically as jerk-optimal polynomial curves. Candidate trajectories are evaluated with a cost function including lateral deviation from the raceline, velocity deviation, curvature deviation, and proximity to surrounding vehicles.

Feasibility checks remove candidates that violate curvature, velocity, track-boundary, or G-G-G-V acceleration constraints. The acceleration checks use [[g_g_g_v_diagrams]] to represent tire, apparent acceleration, and powertrain limits.

The core multi-stage idea is to split the total planning horizon into `M` stages. Each stage generates partial trajectories over a selected partial time horizon, and the end state of a valid partial trajectory becomes the start state for the next stage. Fixed horizon configurations preserve a constant total horizon while allowing different orders of short and long stages.

Because the number of candidates grows exponentially with stage count, the paper proposes four complexity reductions: two-stage planning, coarser sampling in later stages, raceline-biased final-stage samples, and expanding only the lowest-cost first-stage trajectories.

## Key Results

On Yas Marina Circuit simulations, the planner is compared against a single-stage sampling planner and a hybrid graph planner.

In a static obstacle-avoidance scenario at 40 m/s, the multi-stage planner avoids a stationary vehicle while the single-stage planner collides. The hybrid graph planner also avoids the obstacle.

In a full-lap scenario with 13 dynamic opponent vehicles, the multi-stage planner completes the lap in 122.86 s. The single-stage planner takes 128.43 s, and the hybrid graph planner takes 135.57 s with 5 collisions.

In a Turn 5 head-to-head overtaking scenario, the multi-stage planner completes the evaluated maneuver 0.36 s faster than the single-stage planner and 2.24 s faster than the hybrid graph planner. It also merges back to the raceline without lateral overshoot.

The best runtime tradeoff is achieved by expanding only the lowest-cost 10% of first-stage trajectories. This configuration has a median runtime of 43 ms and a maximum of 97 ms, compared with 162 ms median and 456 ms max for the less-pruned two-stage planner.

With opponent prediction errors, the multi-stage planner completes the lap without collisions, while the single-stage and hybrid graph planners record collisions. In 100 reactive-opponent runs, the multi-stage planner achieves 93 successful overtakes with 2 collisions, versus 87 overtakes and 8 collisions for the single-stage planner.

Closed-loop high-fidelity simulation confirms that the generated trajectories are dynamically feasible and trackable with an MPC controller.

## Related Work

This paper complements [[online_velocity_profile_generation_and_tracking_for_sampling_based_local_planning_algorithms_in_autonomous_racing_environments]]. Online velocity profile generation adapts speed along a fixed raceline, while this paper focuses on local multi-stage maneuver generation for dynamic obstacles and overtaking.

It also fits into the planning branch summarized by [[autonomous_vehicles_on_the_edge]], especially sampling-based local planning, graph planning, and multi-vehicle racing.

## Notes / Critique

The strongest idea is fixed discrete partial horizons. This avoids the computational cost of continuous horizon optimization while giving the planner more maneuver diversity than a single-stage setup.

The main weakness is sampling efficiency. End conditions are not yet informed by opponent geometry or tactical context, so the planner wastes computation on many trivially poor candidates. The paper's future-work direction, environment-aware sampling, is the obvious next step.
