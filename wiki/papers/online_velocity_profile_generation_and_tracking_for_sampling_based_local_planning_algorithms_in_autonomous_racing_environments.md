---
tags: [paper]
date: 2026-05-07
task: autonomous_racing
venue: "arXiv 2025"
sources: 1
year: "2025"
url: "https://arxiv.org/abs/2505.05157"
topic:
  - autonomous_racing
  - trajectory_planning
  - online_velocity_planning
  - sampling_based_planning
tech_backbone: []
tech_representation: [g_g_g_v_diagrams]
tech_generation: [online_velocity_profile_generation]
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: [abu_dhabi_autonomous_racing_league]
models_used: []
hardware_used: [cars_and_race_cars]
simulators_used: []
---

# Online Velocity Profile Generation and Tracking for Sampling-Based Local Planning Algorithms in Autonomous Racing Environments

> Online Velocity Profile Generation and Tracking for Sampling-Based Local Planning Algorithms in Autonomous Racing Environments | Langmann, Ogretmen, Werner, and Betz | arXiv:2505.05157

## Summary

This paper proposes an online velocity planner for autonomous racing. Given a fixed three-dimensional raceline, the method recomputes a feasible velocity profile under changing dynamic constraints and provides that profile to a sampling-based local planner.

The motivation is straightforward: offline velocity profiles become stale when grip, tire temperature, rubber buildup, or local constraint scaling changes. If the local planner keeps tracking the old profile, it may either become infeasible or overly conservative.

## Method

The paper uses a three-dimensional track representation with a reference line and road-frame coordinates. Vehicle feasibility is modeled with point-mass acceleration constraints based on G-G diagrams extended by speed and apparent vertical acceleration, closely related to [[g_g_g_v_diagrams]].

The online velocity planner first detects apexes in the upcoming horizon. Candidate apex locations are derived from curvature maxima, then refined by fixed-point iteration to find local minima of admissible velocity.

The upcoming path is split at apexes and solved with a forward-backward velocity-profile generator. Forward passes compute feasible acceleration under positive longitudinal acceleration and engine/power limits. Backward passes compute feasible deceleration toward apexes. The final feasible profile is the pointwise minimum of forward and backward profiles.

The second contribution is a spatial-domain sampling strategy for local planners. Instead of generating trajectories only over a fixed temporal horizon, it generates relative trajectories over a fixed spatial horizon. This better preserves spatial features such as braking points and apex locations when the vehicle starts below the reference speed or deviates from the reference profile.

## Key Results

In simulation on Yas Marina Circuit turns 6 and 7, the authors reduce acceleration limits with a scaling factor `alpha = 0.7` over a 600 m section. A sampling planner using the online velocity profile finishes the section in 13.55 s. Using the offline velocity profile takes 14.97 s, a 1.42 s deficit.

In an obstacle scenario, a static object blocks the raceline and the vehicle starts laterally offset with reduced grip. The online velocity profile improves tracking and produces a 1.18 s sector-time advantage over the offline-profile configuration.

The full planning step averages 114 ms, while online velocity-profile generation alone averages 43 ms in Python on an Intel Core i7-1270P CPU.

## Hardware Used

- [[cars_and_race_cars]]


## Related Work

This method fills a role used by [[challenging_f1_drivers_in_physical_race_cars_with_human_inspired_online_learning]]: when [[apex]] updates local performance-envelope constraints, a velocity planner needs to turn those constraints into a feasible speed reference.

It also extends the [[gripmap]] idea. GripMap can provide local constraint scaling, but the online velocity planner determines how those changing limits should alter braking points, apex speed, and acceleration phases along the raceline.

## Notes / Critique

The main strength is online adaptability with a lightweight solver. The method is practical for racing stacks that want to retain a fixed offline path while adapting speed to changing constraints.

The main limitations are feasibility away from the raceline and missing transient/jerk constraints. The velocity profile is only guaranteed for the fixed path, so overtaking or obstacle avoidance paths need additional checks. The forward-backward solver can also generate abrupt acceleration changes, so smoothing or jerk-constrained extensions are important for physical deployment.
