---
tags: [technique]
date: 2026-05-07
sources: 1
---

# Proximal Policy Optimization

## Definition

Proximal policy optimization is an on-policy actor-critic reinforcement learning algorithm that updates a policy while limiting destructive policy changes during training.

## Key Approaches

In [[champion_level_drone_racing_using_deep_reinforcement_learning]], PPO trains Swift's control policy in quadrotor simulation. The actor maps observations to collective thrust and body-rate commands, while the critic is used only during training and can access privileged simulator information.

## Representative Papers

- [[champion_level_drone_racing_using_deep_reinforcement_learning]]

## Open Problems

For physical racing, PPO policies still require careful reward design, simulator fidelity, and transfer mechanisms. Without realistic perception and dynamics error models, policies trained with PPO can fail under real-world state-estimation noise or dynamics mismatch.
