---
tags: [paper]
date: 2026-05-07
task: autonomous_racing
venue: "arXiv 2026"
sources: 1
year: "2026"
doi: "10.48550/arXiv.2602.15642"
url: "https://arxiv.org/abs/2602.15642"
topic:
  - autonomous_racing
  - trajectory_optimization
  - adaptive_planning
  - controller_feedback
tech_backbone: []
tech_representation: [spatially_aware_adaptive_trajectory_optimization]
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: [f1tenth]
models_used: []
simulators_used: []
---

# Spatially-Aware Adaptive Trajectory Optimization with Controller-Guided Feedback for Autonomous Racing

> Spatially-Aware Adaptive Trajectory Optimization with Controller-Guided Feedback for Autonomous Racing | Wachter, Willert, Ecker, and Hartl-Nesic | arXiv:2602.15642

## Summary

This paper proposes a closed-loop raceline optimization framework that uses controller tracking errors to learn spatial acceleration constraints and reoptimize the trajectory. The core idea is that repeatable tracking errors can reveal local track or vehicle-performance limitations, so the planner should adapt the raceline itself rather than only asking the controller to work harder.

The method is trajectory-centric: it combines NURBS trajectory representation, CMA-ES global optimization, MPC tracking feedback, and an adaptive constraint map.

## Method

The trajectory is represented with cubic NURBS, giving smooth position, velocity, and acceleration continuity around the closed track. A time-optimal parameterization computes feasible lap time under velocity and acceleration limits.

Spatially varying acceleration limits are stored in an adaptive constraint map. Each grid cell scales nominal longitudinal and lateral acceleration limits. The map is updated from execution feedback.

When the MPC tracking controller deviates from the reference trajectory, the method computes a blame region. It partitions the trajectory into acceleration and deceleration zones and attributes the error to the most recent relevant acceleration transition before the deviation. The corresponding map cells are then updated with a Kalman-inspired rule.

CMA-ES optimizes the NURBS control points, weights, and knots under the updated map, producing a revised raceline and timing for the next iterations.

## Key Results

In simulation, adaptive optimization consistently improves lap time over the static version. Reported examples include:

- F1Aut: 20.02 s static to 16.54 s adaptive, a 17.38% improvement.
- Wall1: 16.82 s to 15.71 s.
- Levine: 11.08 s to 10.42 s.
- Operngasse: 7.49 s to 6.24 s.

In a low-friction-region experiment, the system adapts over three laps after discovering two localized low-friction areas, updating the constraint map and changing both trajectory shape and timing.

On real F1TENTH hardware, the authors test low-, medium-, and high-friction tire configurations. Starting from a conservative 7.53 s baseline, the system converges after about 10 laps to 5.73 s, 5.56 s, and 5.29 s respectively, with a reported 7.60% lap-time improvement without explicit friction parameterization or environmental sensing.

## Related Work

This paper is a sibling to [[gripmap_an_efficient_spatially_resolved_constraint_framework_for_offline_and_online_trajectory_planning_in_autonomous_racing]] and [[challenging_f1_drivers_in_physical_race_cars_with_human_inspired_online_learning]]. All three use spatially resolved constraints, but at different points in the stack:

- [[gripmap]] provides a spatial constraint representation.
- [[apex]] learns an executable performance envelope online for a modular full-scale racing stack.
- [[spatially_aware_adaptive_trajectory_optimization]] uses controller tracking error to update constraints and globally reoptimize a NURBS raceline.

It also relates to iterative learning control and learning MPC methods because it exploits repeated laps, but it adapts the global trajectory rather than only feedforward commands or local control policy.

## Notes / Critique

The strongest idea is treating tracking error as information for the planner. The controller is not merely a disturbance-rejection layer; it becomes a sensor that reveals where the trajectory is too aggressive or locally mismatched.

The main limitation is that the constraint map is coupled to the controller and trajectory representation used to generate the feedback. It may not transfer cleanly to a different controller or vehicle without relearning. The paper also uses position tracking error as the main feedback signal, leaving richer temporal and vehicle-state error attribution for future work.
