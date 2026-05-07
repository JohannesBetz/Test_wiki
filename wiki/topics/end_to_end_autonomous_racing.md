---
tags: [topic]
date: 2026-05-06
sources: 3
---

# End-to-End Autonomous Racing

## Definition

End-to-end autonomous racing replaces part or all of the classical perception-planning-control stack with learned policies, usually based on deep networks or reinforcement learning.

## Key Approaches

[[autonomous_vehicles_on_the_edge]] distinguishes partial end-to-end approaches from full end-to-end approaches. Partial systems predict intermediate representations such as waypoints, trajectories, curves, cost maps, or velocity estimates, then pass them to classical controllers. Full end-to-end systems predict controls more directly from sensor inputs.

Methods covered include CNNs, RNNs, LSTMs, fuzzy control, Bayesian optimization, imitation learning, A3C, Q-learning, DDPG, SAC, model-based RL, and curriculum learning.

[[champion_level_drone_racing_using_deep_reinforcement_learning]] is a useful boundary case: the control policy is learned with RL, but the full system is hybrid rather than pure end-to-end. It keeps explicit perception, localization, filtering, and low-level control around the learned policy.

[[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]] is closer to an integrated learned racing policy. GT Sophy maps structured simulator observations directly to throttle/brake and steering, while the simulator provides state and physics.

[[expert_knowledge_driven_reinforcement_learning_for_autonomous_racing_via_trajectory_guidance_and_dynamics_constraints]] is a more structured hybrid. The policy is still learned with RL, but training is explicitly shaped by an expert racing line, a safe dynamics envelope, and curriculum learning.

## Representative Papers

- [[autonomous_vehicles_on_the_edge]]
- [[champion_level_drone_racing_using_deep_reinforcement_learning]]
- [[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]]
- [[expert_knowledge_driven_reinforcement_learning_for_autonomous_racing_via_trajectory_guidance_and_dynamics_constraints]]

## Open Problems

End-to-end racing is constrained by data diversity, out-of-distribution failures, high-speed recovery rarity, sim-to-real transfer, poor interpretability, and the difficulty of learning nonlinear vehicle and tire dynamics. The survey notes that partial end-to-end designs can be more reliable than direct pixel-to-control policies.

Swift supports that pattern: the strongest real-world result comes from combining learned control with structured state estimation and real-world residual modeling.

GT Sophy shows that integrated policies can learn advanced racing tactics when training includes the right opponent distributions and rare decisive scenarios.
