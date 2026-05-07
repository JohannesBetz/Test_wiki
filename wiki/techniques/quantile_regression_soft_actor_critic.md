---
tags: [technique]
date: 2026-05-07
sources: 1
---

# Quantile Regression Soft Actor-Critic

## Definition

Quantile Regression Soft Actor-Critic, or QR-SAC, is the off-policy deep reinforcement learning algorithm used to train [[gt_sophy]]. It extends soft actor-critic with quantile-regression value distributions and N-step returns.

## Key Approaches

In [[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]], QR-SAC learns a policy for continuous throttle/brake and steering control. The critic represents distributions over future rewards instead of only expected value, improving the agent's ability to handle variation in multi-agent racing.

The October race policy used large neural networks with four hidden layers of 2,048 units, dropout on the policy network, Adam optimization, replay buffers, and asynchronous rollout workers connected to PlayStations.

## Representative Papers

- [[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]]

## Open Problems

QR-SAC alone is not enough for champion-level racing. The paper shows that reward design, scenario exposure, opponent diversity, stratified replay sampling, and policy selection are all critical.
