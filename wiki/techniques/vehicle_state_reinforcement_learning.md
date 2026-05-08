---
tags: [technique]
date: 2026-05-08
sources: 1
---

# Vehicle-State Reinforcement Learning

## Definition

Vehicle-state reinforcement learning trains a racing policy from compact dynamic-state observations such as velocities, accelerations, yaw rate, wheel speeds, and track-relative geometry rather than from raw vision alone.

In simulation, this can make policy learning easier and more sample-efficient because the policy receives a cleaner control-oriented state description.

## Key Approach

[[human_professional_level_driving_agent_for_race_car_simulation_environments]] uses PPO on vehicle dynamic signals to learn steering and throttle/brake commands directly.

The approach is especially suitable when:

- the simulator exposes reliable dynamic state,
- the goal is fast control learning rather than perception learning,
- and the researcher wants to study driving behavior near the grip limit with minimal perception confounds.

## Relationship to End-to-End Racing

This technique sits near [[end_to_end_autonomous_racing]], but it is not fully pixel-to-control. It is better understood as state-based end-to-end control learning: the action policy is learned directly, while the observation space is already a structured low-dimensional state.

Compared with vision-based racing RL, it gives up some deployment realism in exchange for a cleaner study of control behavior and reward shaping.

## Representative Papers

- [[human_professional_level_driving_agent_for_race_car_simulation_environments]]

## Open Problems

Open problems include sim-to-real transfer, preventing exploitation of simulator artifacts, and understanding how far structured state input can substitute for raw perception in realistic autonomous racing systems.
