---
tags: [source]
date: 2026-05-07
sources: 1
---

# Langmann Online Velocity Source

> Source: `raw/pdfs/Langmann_OnlineVelocity.pdf`
> Paper: Online Velocity Profile Generation and Tracking for Sampling-Based Local Planning Algorithms in Autonomous Racing Environments, arXiv:2505.05157

## Summary

This paper presents [[online_velocity_profile_generation]] for autonomous racing: a real-time method that recomputes a feasible velocity profile along a fixed three-dimensional raceline when dynamic constraints change. The method is designed for sampling-based local planners that must adapt to grip changes, tire-temperature effects, rubber buildup, and other spatially varying constraints.

The paper is an important bridge between [[g_g_g_v_diagrams]], [[gripmap]], and [[apex]]. G-G-G-V diagrams provide acceleration constraints, GripMap/APEX can update their local scaling online, and this online velocity planner turns those updated constraints into a new reference speed profile for local planning.

## Method

The approach uses a three-dimensional track representation in Frenet-style coordinates around an offline raceline. Vehicle feasibility is represented with point-mass G-G-style acceleration constraints extended by apparent vertical acceleration and velocity.

The method has three main components:

- Online apex detection: identify local minima of feasible velocity by searching around curvature maxima and solving for admissible speed.
- Forward-backward velocity-profile generation: split the upcoming track section at apex locations and compute feasible acceleration/deceleration passes over the fixed path.
- Spatial-domain sampling for local planning: generate relative trajectories over a fixed spatial horizon rather than only a fixed time horizon, so braking points and apex locations remain spatially aligned when the vehicle is off the reference speed profile.

## Evaluation

Experiments are conducted in simulation on Yas Marina Circuit, especially turns 6 and 7. The vehicle corresponds to a Super Formula-style autonomous race car as used in A2RL.

With reduced acceleration limits `alpha = 0.7` between `s = 2000 m` and `s = 2600 m`, the online velocity profile allows the sampling planner to remain feasible and drive the sector in 13.55 s. Using the offline velocity profile leads to poorer feasibility and a 14.97 s sector time, a 1.42 s deficit.

In a multi-vehicle-style scenario with a static obstacle on the raceline and the ego vehicle starting laterally offset, the online velocity profile again improves velocity tracking and yields a 1.18 s sector-time advantage over the offline-profile configuration.

The full trajectory-planning step averages 114 ms, and the online velocity profile generation itself averages 43 ms in a Python implementation on an Intel Core i7-1270P CPU.

## Notes / Critique

The strongest contribution is the planner integration: the method does not just produce a new speed profile; it makes that profile usable for a sampling-based local planner by aligning samples with spatial features such as apexes and braking points.

The main limitations are explicit. The profile is guaranteed feasible only on the fixed raceline, not for arbitrary lateral deviations during overtaking. The point-mass model also neglects transient vehicle dynamics, and the forward-backward solver can produce high-jerk acceleration transitions that may stress actuators or controllers.

## Pages Created From This Source

- [[online_velocity_profile_generation_and_tracking_for_sampling_based_local_planning_algorithms_in_autonomous_racing_environments]]
- [[online_velocity_profile_generation]]
