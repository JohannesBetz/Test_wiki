---
tags: [technique]
date: 2026-05-06
sources: 1
---

# Reinforcement Learning

## Definition

Reinforcement learning trains an agent to maximize cumulative reward through interaction with an environment. In autonomous racing, the reward often combines progress, lap time, track keeping, collision avoidance, and overtaking behavior.

## Key Approaches

[[autonomous_vehicles_on_the_edge]] covers A3C, Q-learning with state representation learning, DDPG, SAC, imitation learning, Bayesian decision making, model-based RL, curriculum learning, and verification-oriented RL experiments. RL is mostly used in [[end_to_end_autonomous_racing]], often through [[f1tenth_gym]], [[torcs]], [[svl_simulator]], Roborace Simulator, or game environments.

## Representative Papers

- [[autonomous_vehicles_on_the_edge]]

## Open Problems

The survey notes generalization, sim-to-real transfer, oscillatory control on real vehicles, data diversity, and safety under rare high-speed failure states as core RL barriers.
