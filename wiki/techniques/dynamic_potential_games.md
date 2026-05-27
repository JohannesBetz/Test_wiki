---
tags: [technique]
date: 2026-05-27
sources: 1
---

# Dynamic Potential Games

## Definition

Dynamic potential games are a game-theoretic planning formulation for multi-agent sequential decision problems in which the coupled evolution of agent strategies can be organized through a potential-like dynamic structure.

In autonomous racing, this matters because it offers a way to preserve explicit strategic interaction while still aiming for tractable online planning.

## Key Approach

[[autonomous_racing_with_dynamic_games]] is the anchor paper for this technique in the vault.

The method appears to use dynamic potential games as the strategic backbone and `RAPID` as the scalable planner layered on top.

The practical appeal is straightforward:

- keep the racing interaction explicitly multi-agent,
- reason over overtaking and blocking as strategic behavior,
- and reduce the computational burden enough that the formulation can still be used for planning.

## Relationship to Racing Planning

This technique belongs primarily inside [[autonomous_racing_planning]] and secondarily inside [[autonomous_vehicle_racing]].

Compared with [[dynamic_near_potential_functions]], it seems less focused on learning an offline surrogate and more focused on structuring the online game itself.

Compared with [[learned_model_predictive_game]], it is a more classical game-theoretic route with less emphasis on learned interaction modeling.

## Representative Papers

- [[autonomous_racing_with_dynamic_games]]

## Open Problems

Open problems include:

- scaling dynamic-game reasoning beyond a small number of racing agents,
- preserving solution quality when approximation is needed for real-time execution,
- handling uncertainty and partial observability in the game state,
- and deciding when a dynamic-potential reformulation remains faithful enough to the underlying competitive race dynamics.
