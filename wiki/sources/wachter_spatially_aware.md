---
tags: [source]
date: 2026-05-07
sources: 1
---

# Wachter Spatially Aware Source

> Source: `raw/pdfs/Wachter_SpatiallyAware.pdf`
> Paper: Spatially-Aware Adaptive Trajectory Optimization with Controller-Guided Feedback for Autonomous Racing, arXiv:2602.15642

## Summary

This paper proposes [[spatially_aware_adaptive_trajectory_optimization]], a closed-loop raceline optimization framework that uses controller tracking errors as feedback for global trajectory improvement. Instead of treating tracking error only as a controller problem, the method interprets repeatable errors as evidence that the planned trajectory or local acceleration constraints should be changed.

The paper is closely related to [[gripmap]] and [[apex]], but its emphasis is different. GripMap stores spatially resolved constraints, APEX learns an online executable performance envelope, and this paper uses tracking-error feedback to reshape a NURBS raceline and its timing through CMA-ES optimization.

## Method

The framework combines:

- NURBS trajectory representation for smooth closed-loop racelines.
- Time-optimal parameterization under spatially varying acceleration constraints.
- Adaptive constraint maps that locally scale nominal longitudinal and lateral acceleration limits.
- Blame-region computation to attribute tracking errors to the preceding acceleration/deceleration phase.
- Kalman-inspired constraint-map updates.
- CMA-ES global trajectory optimization.
- MPC tracking control that supplies execution feedback.

The key design move is to shift learning from local controller adaptation to trajectory-centric optimization. If the controller repeatedly struggles in a region, the trajectory is globally reoptimized using a locally updated constraint map.

## Evaluation

The authors evaluate the approach in simulation and on an F1TENTH-scale racecar. In simulation, adaptive optimization improves lap times across several tracks. The largest reported gain is on F1Aut, where lap time improves from 20.02 s with the static version to 16.54 s with adaptation, a 17.38% reduction.

In a local-friction-variation experiment, the method adapts over three laps after encountering two low-friction regions. Tracking error updates the blame region, and the optimizer changes both trajectory shape and timing.

On real hardware, the authors test different tire configurations representing low, medium, and high friction. The baseline lap time is 7.53 s, and the adaptive system converges after roughly 10 laps to 5.73 s, 5.56 s, and 5.29 s for low-, medium-, and high-friction configurations. The paper reports a 7.60% lap-time improvement without explicit friction parameterization or environmental sensing.

## Notes / Critique

The strongest contribution is the use of execution feedback to update the global trajectory itself, not only the controller or a velocity profile. The blame-region idea is useful because tracking errors are delayed effects; the location where the vehicle deviates is not always the location where the trajectory became too aggressive.

The main caveat is controller dependency. The learned map reflects how a specific MPC/controller tracks a specific trajectory representation. The authors also flag future work on evaluating different control architectures, richer error metrics, and learning-based origin-region identification.

## Pages Created From This Source

- [[spatially_aware_adaptive_trajectory_optimization_with_controller_guided_feedback_for_autonomous_racing]]
- [[spatially_aware_adaptive_trajectory_optimization]]
