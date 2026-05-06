---
tags: [topic]
date: 2026-05-06
sources: 1
---

# Autonomous Racing Simulation

## Definition

Autonomous racing simulation provides synthetic tracks, vehicle dynamics, sensors, opponents, and interfaces for developing and evaluating autonomous racing algorithms.

## Key Approaches

[[autonomous_vehicles_on_the_edge]] lists several simulation environments:

- [[torcs]] for lightweight 3D racing simulation with tracks, vehicles, NPC opponents, and vehicle physics.
- Learn-to-Race / Roborace Simulator for Roborace-style control and reinforcement learning.
- [[svl_simulator]] for end-to-end autonomous vehicle simulation with racing vehicles and maps.
- [[f1tenth_gym]] and F1TENTH Simulator for small-scale racing and RL.
- [[carla]]-based CI/testing frameworks for racing software evaluation.

## Representative Papers

- [[autonomous_vehicles_on_the_edge]]

## Open Problems

Simulation must balance high-fidelity vehicle dynamics, sensor realism, opponent behavior, scalable RL interfaces, and sim-to-real transfer. The survey also points to scenario generation for multi-vehicle maneuvers as an important testing need.
