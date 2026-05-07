---
tags: [technique]
date: 2026-05-07
sources: 2
---

# Soft Actor-Critic

## Definition

Soft Actor-Critic is an off-policy maximum-entropy reinforcement learning algorithm for continuous control. It optimizes both expected reward and policy entropy, encouraging exploration and robust behavior.

## Key Approaches

In [[outplaying_elite_table_tennis_players_with_an_autonomous_robot]], SAC trains Ace's rally policies in simulation. Policies map noisy ball/robot histories to abstract actions every 32 ms, which are then converted into feasible robot trajectory constraints.

[[quantile_regression_soft_actor_critic]] is a related SAC extension used by [[gt_sophy]] for high-fidelity simulated automobile racing.

[[learn_consolidate_dominate_orchestrating_cognitive_skill_distillation_and_alternating_learning_for_autonomous_racing]] uses SAC as the base RL algorithm inside [[csdal]], with added temporal distillation and curriculum-learning modules.

## Representative Papers

- [[outplaying_elite_table_tennis_players_with_an_autonomous_robot]]
- [[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]]
- [[learn_consolidate_dominate_orchestrating_cognitive_skill_distillation_and_alternating_learning_for_autonomous_racing]]

## Open Problems

For physical systems, SAC still depends heavily on simulator quality, observation modeling, reward design, and safety wrappers that keep learned actions executable.
