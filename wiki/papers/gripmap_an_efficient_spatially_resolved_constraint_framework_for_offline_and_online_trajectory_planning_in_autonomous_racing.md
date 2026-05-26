---
tags: [paper]
date: 2026-05-07
task: autonomous_racing
venue: "arXiv 2025"
sources: 1
year: "2025"
doi: "10.48550/arXiv.2504.12115"
url: "https://arxiv.org/abs/2504.12115"
topic:
  - autonomous_racing
  - trajectory_planning
  - motion_control
  - vehicle_dynamics
  - friction_mapping
tech_backbone: []
tech_representation: [gripmap, g_g_g_v_diagrams]
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: [indy_autonomous_challenge]
models_used: []
hardware_used: [cars_and_race_cars]
simulators_used: []
---

# GripMap: An Efficient, Spatially Resolved Constraint Framework for Offline and Online Trajectory Planning in Autonomous Racing

> GripMap: An Efficient, Spatially Resolved Constraint Framework for Offline and Online Trajectory Planning in Autonomous Racing | arXiv:2504.12115 | Werner, Schwehn, Lienkamp, and Betz

## Summary

This paper proposes [[gripmap]], a spatially resolved constraint framework for autonomous racing planners. Instead of treating vehicle dynamics as globally invariant across the track, GripMap stores local scaling factors in a Frenet-frame grid and uses them to scale baseline [[g_g_g_v_diagrams|G-G-G-V]] acceleration limits.

The key claim is that planners should reason about the usable dynamic potential of the whole vehicle-software-track system, not only the nominal tire-road friction coefficient. Local grip can drop off the racing line because of dust, debris, rain, or lack of rubber buildup, and local software limitations can also reduce usable acceleration even when the physical vehicle might have more grip available.

## Method

GripMap discretizes the track in Frenet coordinates `(s, n)`, where `s` follows the reference line and `n` is lateral offset. Each cell stores a local dimensionless scaling factor `theta_ij`. In the demonstrated point-mass setup, this factor multiplies the baseline longitudinal and lateral acceleration limits obtained from G-G-G-V constraints.

The indexing is designed for online use. Continuous Frenet coordinates are converted directly to integer cell indices, clipped to valid bounds, and used to retrieve the scaling factor from a dense matrix. The paper describes this as a perfect-hash-inspired lookup: access is constant time, cache-friendly, and avoids the memory waste of a Cartesian grid over off-track regions.

The framework is integrated into two planning stages:

- Offline raceline optimization: a minimum-lap-time optimal-control problem uses GripMap-scaled G-G-G-V constraints when generating the reference trajectory.
- Online sampling-based planning: candidate trajectories are evaluated against local GripMap constraints. Rather than rejecting every local limit exceedance, the planner can add a soft cost, which lets it trade small grip overuse against opponent avoidance or race-strategy needs.

## Key Results

At Yas Marina Circuit in the A2RL context, iterative GripMap refinement produced local scaling factors between 75% and 100% of the baseline acceleration estimate. A globally conservative planner would need to use 75% everywhere, but GripMap keeps that conservative value only where needed. The reported lap-time improvement over the global 75% baseline is 5.2%.

In a ROS2 Python runtime test, the online planner sampled 1,000 trajectories per planning step with 40 discretization points each. GripMap-informed planning averaged 0.1565 s, while the baseline without GripMap averaged 0.1553 s. The added overhead is about 0.77%.

The paper also revisits a Las Vegas Motor Speedway IAC spin-out. The original planner assumed enough grip for an outside overtake on a dusty banked turn. A high-fidelity resimulation with reduced off-line grip reproduced the failure, while GripMap-informed planning reduced corner-entry speed by up to 7 m/s, moved the planned trajectory toward a higher-grip region, and kept planned tire utilization within the local limit.

## Hardware Used

- [[cars_and_race_cars]]


## Related Work

The paper extends the acceleration-envelope view captured by [[g_g_g_v_diagrams]] and is a natural follow-up to [[a_quasi_steady_state_black_box_simulation_approach_for_the_generation_of_g_g_g_v_diagrams]]. It also relates to [[time_optimal_trajectory_planning_for_a_race_car_considering_variable_tyre_road]], which considered variable tire-road friction in offline trajectory optimization but not high-frequency online replanning.

For the broader autonomous racing stack, GripMap sits between offline raceline generation and online interaction-aware planning, making it directly relevant to [[autonomous_racing_planning]], [[autonomous_racing_control]], and the [[indy_autonomous_challenge]] setting.

## Notes / Critique

The strongest contribution is the low-overhead representation. Spatially varying grip constraints are valuable only if online planners can query them cheaply, and the paper shows that a Frenet-grid lookup can be added with negligible runtime impact.

The main open issue is how to fill and update the map. The paper uses iterative real-world tuning and empirical extrapolation away from the raceline. That is pragmatic, but it means GripMap quality depends on available track data, validation laps, and engineering judgment. The authors explicitly frame real-time self-identification of GripMap values as future work.
