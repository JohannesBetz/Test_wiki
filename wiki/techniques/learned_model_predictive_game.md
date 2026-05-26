---
tags: [technique]
date: 2026-05-20
sources: 1
---

# Learned Model Predictive Game

## Definition

A learned model predictive game is a planning approach that combines receding-horizon model-predictive reasoning with an explicit multi-agent game formulation, while using learned components to make the interaction model fast or expressive enough for real-time deployment.

In drone racing, this is useful when the agent must not only fly aggressively, but also anticipate and strategically respond to the moves of other drones at high speed.

## Key Approach

[[strategizing_at_speed_a_learned_model_predictive_game_for_multi_agent_drone_racing]] is the anchor paper for this technique in the vault.

The title suggests a three-way hybrid:

- `model predictive` for short-horizon online replanning,
- `game` for strategic multi-agent interaction,
- and `learned` for computational tractability or richer interaction modeling.

The core appeal is that it preserves strategic structure while acknowledging that a full online dynamic game may otherwise be too slow for agile racing.

## Relationship to Drone Racing and Game-Theoretic Planning

This technique belongs most directly near [[autonomous_drone_racing]] and secondarily near [[model_predictive_control]].

Compared with [[multi_agent_time_optimal_motion_planning]], it emphasizes strategic interaction rather than only joint time efficiency.

Compared with ground-racing methods such as [[dynamic_near_potential_functions]], it appears to bring a similar game-theoretic spirit into a faster and more aerially unconstrained embodiment.

## Representative Papers

- [[strategizing_at_speed_a_learned_model_predictive_game_for_multi_agent_drone_racing]]

## Open Problems

Open problems include scaling to larger drone fields, handling partial observability and communication limits, deciding which parts of the interaction model should be learned versus explicit, and proving that the learned game approximation preserves useful strategic behavior under aggressive closed-loop flight.
