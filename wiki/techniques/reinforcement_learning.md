---
tags: [technique]
date: 2026-05-06
sources: 5
---

# Reinforcement Learning

## Definition

Reinforcement learning trains an agent to maximize cumulative reward through interaction with an environment. In autonomous racing, the reward often combines progress, lap time, track keeping, collision avoidance, and overtaking behavior.

## Key Approaches

[[autonomous_vehicles_on_the_edge]] covers A3C, Q-learning with state representation learning, DDPG, SAC, imitation learning, Bayesian decision making, model-based RL, curriculum learning, and verification-oriented RL experiments. RL is mostly used in [[end_to_end_autonomous_racing]], often through [[f1tenth_gym]], [[torcs]], [[svl_simulator]], Roborace Simulator, or game environments.

[[champion_level_drone_racing_using_deep_reinforcement_learning]] shows model-free on-policy RL, specifically [[proximal_policy_optimization]], deployed on a physical drone-racing system. Its key contribution is coupling RL with [[sim_to_real_transfer]] through learned perception and dynamics residuals.

[[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]] shows model-free off-policy RL in high-fidelity multi-agent racing. Its key additions are [[quantile_regression_soft_actor_critic]], [[mixed_scenario_training]], and reward terms for competitive behavior under [[racing_etiquette]] constraints.

[[outplaying_elite_table_tennis_players_with_an_autonomous_robot]] shows model-free RL on a physical high-speed robot. Ace uses [[soft_actor_critic]] with an [[asymmetric_actor_critic]] setup to train rally policies in simulation that transfer to noisy real-world table-tennis perception.

[[learn_consolidate_dominate_orchestrating_cognitive_skill_distillation_and_alternating_learning_for_autonomous_racing]] shows SAC-based autonomous racing enhanced with [[knowledge_distillation]] and [[curriculum_learning]] to improve sample efficiency, skill retention, and lap time.

## Representative Papers

- [[autonomous_vehicles_on_the_edge]]
- [[champion_level_drone_racing_using_deep_reinforcement_learning]]
- [[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]]
- [[outplaying_elite_table_tennis_players_with_an_autonomous_robot]]
- [[learn_consolidate_dominate_orchestrating_cognitive_skill_distillation_and_alternating_learning_for_autonomous_racing]]

## Open Problems

The survey notes generalization, sim-to-real transfer, oscillatory control on real vehicles, data diversity, and safety under rare high-speed failure states as core RL barriers.

Swift confirms that those barriers can be reduced but not eliminated: the policy achieves champion-level performance, yet remains sensitive to crash recovery, opponent awareness, and visual appearance shifts.

GT Sophy adds another barrier: high-performance RL agents can learn speed and tactics, but imprecise human norms require careful reward design, opponent populations, scenario exposure, and human-in-the-loop policy selection.

Ace adds the difficulty of learning from surrogate objectives when the true match objective depends on human opponent behavior that is not fully modeled in simulation.

CSDAL adds the challenge of relying on expert demonstrations without letting the student policy remain bounded by expert performance.
