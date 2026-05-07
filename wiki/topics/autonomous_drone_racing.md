---
tags: [topic]
date: 2026-05-07
sources: 1
---

# Autonomous Drone Racing

## Definition

Autonomous drone racing studies quadrotors flying through 3D racing tracks at high speed, often through gates, while perceiving and controlling from onboard sensors. It is a key subdomain of [[Highly_dynamic_autonomous_system|highly dynamic autonomous systems]].

## Key Approaches

- Gate detection and gate-relative localization.
- [[visual_inertial_odometry]] with drift correction.
- Time-optimal trajectory generation and MPC.
- Deep [[reinforcement_learning]] policies trained in simulation.
- [[sim_to_real_transfer]] using domain randomization or real-world residual modeling.
- Perception-aware planning/control that trades pure speed against keeping gates visible.

## Representative Papers

- [[champion_level_drone_racing_using_deep_reinforcement_learning]]

## Open Problems

Open problems include robust perception under motion blur and lighting changes, onboard-only state estimation, crash recovery, opponent-aware racing strategy, sim-to-real transfer, and safety-performance tradeoffs under severe latency and actuation constraints.
