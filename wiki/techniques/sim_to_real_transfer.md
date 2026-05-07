---
tags: [technique]
date: 2026-05-07
sources: 2
---

# Sim-to-Real Transfer

## Definition

Sim-to-real transfer moves policies, models, or controllers trained in simulation onto physical systems despite mismatches in sensing, dynamics, latency, and environment appearance.

## Key Approaches

In [[champion_level_drone_racing_using_deep_reinforcement_learning]], sim-to-real transfer is handled by fitting empirical residual models from real-world rollouts and injecting those residuals into simulation before fine-tuning the policy. This differs from broad domain randomization: the simulator is made more realistic using short, targeted real-world experience on the race track.

In [[outplaying_elite_table_tennis_players_with_an_autonomous_robot]], sim-to-real transfer relies on noisy sensor histories, simulator noise models, physics perturbations, and an [[asymmetric_actor_critic]] setup where the critic learns from privileged simulator truth while the policy learns to act from deployment-like observations.

## Representative Papers

- [[champion_level_drone_racing_using_deep_reinforcement_learning]]
- [[outplaying_elite_table_tennis_players_with_an_autonomous_robot]]

## Open Problems

The main challenge is learning enough about real-world error modes without requiring so much track-specific data that the method loses generality. Appearance changes, sensing failures, actuator degradation, and opponent interactions remain difficult to simulate faithfully.
