---
tags: [model]
date: 2026-05-07
sources: 1
---

# GT Sophy

## Definition

GT Sophy, or Gran Turismo Sophy, is the championship-level racing agent introduced in [[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]]. It is trained with model-free deep reinforcement learning to drive and race in [[gran_turismo_sport]].

## Key Approaches

- [[quantile_regression_soft_actor_critic]] for off-policy actor-critic learning.
- Course-point track representation in the car's egocentric frame.
- Opponent-state encoding for nearby cars in front and behind.
- Reward shaping for progress, passing, off-course behavior, collision avoidance, and [[racing_etiquette]].
- [[mixed_scenario_training]] to expose the policy to rare but decisive racing situations.
- Human-reviewed policy selection to trade off speed, tactics, collisions, and sportsmanship.

## Representative Papers

- [[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]]

## Open Problems

GT Sophy still lacks mature high-level race strategy. It may pass too early, attack opponents that will soon serve penalties, or make locally strong choices that create future slipstream vulnerability.
