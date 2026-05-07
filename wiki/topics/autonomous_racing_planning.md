---
tags: [topic]
date: 2026-05-06
sources: 3
---

# Autonomous Racing Planning

## Definition

Autonomous racing planning computes racelines, local trajectories, and high-level behavior for a racecar driving near its dynamic limits.

## Key Approaches

[[autonomous_vehicles_on_the_edge]] separates planning into three layers:

- Global planning: minimum-time, minimum-curvature, energy-aware, geometric, evolutionary, and optimal-control raceline generation.
- Local planning: obstacle avoidance and dynamic feasibility using MPC, graph search, splines, RRT variants, clothoids, sampled motion primitives, and stochastic prediction.
- Behavioral planning: overtaking, blocking, interaction, race-control response, and cost/game-theoretic selection among candidate maneuvers.

[[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]] gives a contrasting learned-policy approach: GT Sophy does not explicitly decompose racing into planning and control modules, but learns tactical behaviors such as passing, blocking, draft disruption, and emergency maneuvers from mixed scenarios.

[[learn_consolidate_dominate_orchestrating_cognitive_skill_distillation_and_alternating_learning_for_autonomous_racing]] uses a learned policy to modify an expert reference path and velocity profile, then relies on a lower-level NMPC tracker for feasible vehicle control.

## Representative Papers

- [[autonomous_vehicles_on_the_edge]]
- [[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]]
- [[learn_consolidate_dominate_orchestrating_cognitive_skill_distillation_and_alternating_learning_for_autonomous_racing]]

## Open Problems

Major gaps include multi-vehicle planning at high speed, recursive feasibility under dynamic constraints, real-time replanning, non-convex collision avoidance, interaction with non-cooperative agents, and decision making under high uncertainty.

GT Sophy suggests that scenario design and opponent diversity can partly substitute for explicit behavior-planning rules, but long-horizon race strategy remains open.
