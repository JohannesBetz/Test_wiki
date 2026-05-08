---
tags: [topic]
date: 2026-05-06
sources: 5
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

[[out_of_distribution_generalization_with_a_sparc_racing_100_unseen_vehicles_with_a_single_policy]] focuses on a different weakness of learned racing policies: [[sparc]] adds contextual online adaptation so one policy can handle many unseen vehicle variants without explicit context labels at test time.

[[a_champion_level_vision_based_reinforcement_learning_agent_for_competitive_racing_in_gran_turismo_7]] focuses on privileged-information reduction: [[asymmetric_recurrent_actor_critic]] shows that champion-level competitive racing is possible from egocentric vision and onboard sensing, while still using privileged critic information during training.

## Representative Papers

- [[autonomous_vehicles_on_the_edge]]
- [[champion_level_drone_racing_using_deep_reinforcement_learning]]
- [[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]]
- [[expert_knowledge_driven_reinforcement_learning_for_autonomous_racing_via_trajectory_guidance_and_dynamics_constraints]]
- [[out_of_distribution_generalization_with_a_sparc_racing_100_unseen_vehicles_with_a_single_policy]]
- [[a_champion_level_vision_based_reinforcement_learning_agent_for_competitive_racing_in_gran_turismo_7]]

## Open Problems

End-to-end racing is constrained by data diversity, out-of-distribution failures, high-speed recovery rarity, sim-to-real transfer, poor interpretability, and the difficulty of learning nonlinear vehicle and tire dynamics. The survey notes that partial end-to-end designs can be more reliable than direct pixel-to-control policies.

Swift supports that pattern: the strongest real-world result comes from combining learned control with structured state estimation and real-world residual modeling.

GT Sophy shows that integrated policies can learn advanced racing tactics when training includes the right opponent distributions and rare decisive scenarios.

SPARC sharpens the generalization problem: even if an end-to-end policy is fast, it may still be brittle under hidden dynamics shifts unless it can infer and adapt to context online.

Vision-based GT7 racing sharpens a different realism problem: policies that rely less on privileged localization are more deployment-relevant, but they must solve partial observability and appearance robustness much more directly.
