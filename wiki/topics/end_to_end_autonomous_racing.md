---
tags: [topic]
date: 2026-05-06
sources: 1
---

# End-to-End Autonomous Racing

## Definition

End-to-end autonomous racing replaces part or all of the classical perception-planning-control stack with learned policies, usually based on deep networks or reinforcement learning.

## Key Approaches

[[autonomous_vehicles_on_the_edge]] distinguishes partial end-to-end approaches from full end-to-end approaches. Partial systems predict intermediate representations such as waypoints, trajectories, curves, cost maps, or velocity estimates, then pass them to classical controllers. Full end-to-end systems predict controls more directly from sensor inputs.

Methods covered include CNNs, RNNs, LSTMs, fuzzy control, Bayesian optimization, imitation learning, A3C, Q-learning, DDPG, SAC, model-based RL, and curriculum learning.

## Representative Papers

- [[autonomous_vehicles_on_the_edge]]

## Open Problems

End-to-end racing is constrained by data diversity, out-of-distribution failures, high-speed recovery rarity, sim-to-real transfer, poor interpretability, and the difficulty of learning nonlinear vehicle and tire dynamics. The survey notes that partial end-to-end designs can be more reliable than direct pixel-to-control policies.
