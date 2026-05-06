---
tags: [topic]
date: 2026-05-06
sources: 1
---

# Autonomous Racing Planning

## Definition

Autonomous racing planning computes racelines, local trajectories, and high-level behavior for a racecar driving near its dynamic limits.

## Key Approaches

[[autonomous_vehicles_on_the_edge]] separates planning into three layers:

- Global planning: minimum-time, minimum-curvature, energy-aware, geometric, evolutionary, and optimal-control raceline generation.
- Local planning: obstacle avoidance and dynamic feasibility using MPC, graph search, splines, RRT variants, clothoids, sampled motion primitives, and stochastic prediction.
- Behavioral planning: overtaking, blocking, interaction, race-control response, and cost/game-theoretic selection among candidate maneuvers.

## Representative Papers

- [[autonomous_vehicles_on_the_edge]]

## Open Problems

Major gaps include multi-vehicle planning at high speed, recursive feasibility under dynamic constraints, real-time replanning, non-convex collision avoidance, interaction with non-cooperative agents, and decision making under high uncertainty.
