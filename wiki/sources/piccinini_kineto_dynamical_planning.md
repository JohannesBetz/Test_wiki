---
tags: [source]
date: 2026-05-07
sources: 1
---

# Piccinini Kineto-Dynamical Planning Source

> Source: `raw/pdfs/Piccinini_Kineto_Dynamical_Planning.pdf`
> Paper: Kineto-Dynamical Planning and Accurate Execution of Minimum-Time Maneuvers on Three-Dimensional Circuits, arXiv:2502.03454

## Summary

This paper introduces [[kineto_dynamical_planning]], a 3D-track minimum-time planning framework that combines a learned kineto-dynamical vehicle model with economic nonlinear model predictive control. The central claim is that online autonomous racing on banked and sloped circuits needs a planning model that is richer than a point-mass approximation but still cheap enough for repeated real-time replanning.

The paper matters to this vault because it sits directly at the boundary between [[autonomous_racing_planning]] and [[autonomous_racing_control]]. It learns dynamic limits online, plans with 3D-aware acceleration constraints, and then tests whether those plans can actually be executed by a high-fidelity simulated racecar close to the minimum-lap-time optimum.

## Method

The system is an artificial race driver that integrates:

- A new [[kineto_dynamical_planning]] model with yaw-rate, lateral-velocity, longitudinal-acceleration, and curvilinear-track states.
- 3D road geometry with slope, banking, and nonplanar curvature terms.
- Learned G-G-V-style acceleration constraints that shift and scale with gravity and vertical acceleration.
- Economic NMPC for minimum-time trajectory planning in curvilinear coordinates.
- A multi-round learning loop that refines the dynamic model, low-level controllers, and vertical-load correction term while driving.

Unlike quasi-steady-state methods, the framework does not require direct access to the simulator equations. It estimates performance from open-loop and closed-loop driving data, then refines the most sensitive vertical-acceleration scaling term with an online Nelder-Mead search.

## Evaluation

The authors evaluate the method on the Mugello circuit with a high-fidelity double-track sports-car simulator. After five learning rounds, the artificial race driver reaches a lap time of 115.322 s, only 0.724 s slower than the offline minimum-lap-time solution computed with the same simulator.

The paper also compares against a 3D point-mass benchmark. The new kineto-dynamical model gives better closed-loop performance because it predicts lateral velocity and avoids overoptimistic acceleration envelopes that look fast offline but become infeasible during execution.

The 3D-track result is especially notable: the learned driver is 3.5 s faster on the real 3D Mugello geometry than on an artificial flattened 2D version, showing how much slope and banking matter for minimum-time planning.

## Notes / Critique

The strongest part is the explicit closed-loop comparison with a high-fidelity minimum-lap-time baseline. That makes the contribution more concrete than papers that only show an offline planning improvement.

The main limitation is that the validation is still simulator-only, and the learning loop is specialized to a repeated-lap setting on one track. The paper also still relies on hand-designed model structure even though several coefficients are learned from data.

## Pages Created From This Source

- [[kineto_dynamical_planning_and_accurate_execution_of_minimum_time_maneuvers_on_three_dimensional_circuits]]
- [[kineto_dynamical_planning]]
