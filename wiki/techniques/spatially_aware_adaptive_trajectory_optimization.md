---
tags: [technique]
date: 2026-05-07
sources: 1
---

# Spatially Aware Adaptive Trajectory Optimization

## Definition

Spatially aware adaptive trajectory optimization uses repeated execution feedback to update location-specific constraints and reoptimize the trajectory over a track.

In autonomous racing, the method treats consistent controller tracking errors as evidence that the planned raceline, timing, or local acceleration limits should be changed.

## Key Approach

[[spatially_aware_adaptive_trajectory_optimization_with_controller_guided_feedback_for_autonomous_racing]] implements this idea with:

- NURBS raceline representation.
- Adaptive spatial acceleration constraint maps.
- Blame-region computation for delayed tracking-error attribution.
- Kalman-inspired map updates.
- CMA-ES global trajectory optimization.
- MPC tracking feedback.

## Relationship to GripMap and APEX

[[gripmap]] stores spatial constraints. [[apex]] learns local performance-envelope scaling for online planning/control. Spatially aware adaptive trajectory optimization instead uses controller feedback to update a global trajectory optimizer, changing both raceline shape and timing.

## Representative Papers

- [[spatially_aware_adaptive_trajectory_optimization_with_controller_guided_feedback_for_autonomous_racing]]

## Open Problems

Open problems include controller dependence, richer feedback signals beyond position error, better causal attribution of delayed errors, and scaling from F1TENTH hardware to full-size autonomous race cars.
