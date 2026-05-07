---
tags: [technique]
date: 2026-05-07
sources: 1
---

# Mixed Scenario Training

## Definition

Mixed scenario training trains a single policy across a deliberately mixed set of full-task and specialized scenarios, so rare but important behaviors are encountered often enough to be learned and retained.

## Key Approaches

[[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]] uses mixed scenario training to teach [[gt_sophy]] both general racing and specific skills. Scenarios include solo driving, nearby opponents, crowded starts, slipstream passing, difficult chicanes, and mistake-recovery launch states.

Unlike a sequential curriculum, all scenarios remain present throughout training. Multi-table stratified sampling enforces scenario proportions in replay mini-batches so skills such as slipstream passing do not vanish due to random replay-buffer imbalance.

## Representative Papers

- [[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]]

## Open Problems

The main design problem is choosing the scenarios and sampling ratios. This often requires expert human judgment about which situations will decide a race.
