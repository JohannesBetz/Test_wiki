---
tags: [topic]
date: 2026-05-06
sources: 2
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

[[human_professional_level_driving_agent_for_race_car_simulation_environments]] adds a simulator-analysis perspective: TORCS can be strong enough to train near-professional driving behavior, but it can also reward policies that exploit actuator and tire-model simplifications that would be suspect on a real vehicle.

[[enhancing_generalization_in_autonomous_driving_through_track_agnostic_reinforcement_learning]] adds a simulator-diversity perspective: the same track-agnostic PPO idea is tested in both a custom 2D sensor-based environment and a richer 3D TrackMania setup, using simulation variety itself as a generalization stress test.

## Representative Papers

- [[autonomous_vehicles_on_the_edge]]
- [[human_professional_level_driving_agent_for_race_car_simulation_environments]]
- [[enhancing_generalization_in_autonomous_driving_through_track_agnostic_reinforcement_learning]]

## Open Problems

Simulation must balance high-fidelity vehicle dynamics, sensor realism, opponent behavior, scalable RL interfaces, and sim-to-real transfer. The survey also points to scenario generation for multi-vehicle maneuvers as an important testing need.

The Bari paper adds a realism-audit problem: a simulator may produce very fast agents whose driving style is partly shaped by unrealistic actuation or contact models, so simulator success needs qualitative scrutiny as well as lap-time metrics.

Track-agnostic RL adds a benchmark-design problem: if a simulator exposes centerlines or other privileged geometry too directly, agents may look robust while actually overfitting to track-specific features that disappear on new layouts.
