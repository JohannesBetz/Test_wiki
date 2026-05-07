---
tags: [source]
date: 2026-05-07
sources: 1
---

# Vries Competitor-Aware Race Management Source

> Source: `raw/pdfs/Vries_Competitor-aware_race_management.pdf`
> Paper: A Competitor-aware Race Management Policy: A Game Theoretical Approach, TU/e MSc Thesis, 2026

## Summary

This thesis studies autonomous electric endurance racing as a race-management problem rather than only a trajectory-tracking or lap-time-optimization problem. The key claim is that when energy is scarce and aerodynamic interactions matter, winning strategies depend on competitor-aware decisions about battery deployment, slipstreaming, overtaking, and pit timing over the whole race.

The work is especially relevant to this vault because it pushes autonomous racing planning upward in time scale. Instead of focusing on a single lap or a short local planning horizon, it models race outcome over many laps and treats the interaction as a multi-agent game.

## Method

The proposed framework is bi-level.

- Lower level: a multi-agent game-theoretic optimal-control problem models a single lap with ribbon-track vehicle dynamics, energy consumption, aerodynamic wake effects, and asymmetric motorsport-style collision-avoidance constraints.
- Middle bridge: a neural surrogate approximates the single-lap game outcome as a lap-to-lap state-transition model over energy allocation and time gap.
- Upper level: reinforcement learning uses that surrogate environment to learn full-race strategy, including energy allocation, pit-stop decisions, and charging amounts.

The paper focuses on two-agent electric endurance racing and uses finishing position, not minimum lap time, as the main strategic objective.

## Evaluation

The thesis demonstrates the framework on a two-agent 45-lap race. The abstract and core results emphasize that aerodynamic interactions are decisive: policies that exploit slipstream energy savings can beat strategies that look better from a single-agent minimum-time perspective.

The main conceptual result is that race-winning behavior differs fundamentally from isolated lap-time optimization. Because the reward is finishing position, the agent may deliberately sacrifice local lap time to preserve battery energy, secure later overtaking opportunities, or defend a strategically valuable track position.

## Notes / Critique

The strongest contribution is the time-scale separation. The thesis acknowledges that short-horizon multi-agent planners can model local interaction but often miss race-long battery and pit-strategy consequences.

The main limitation is scope. The framework is restricted to two agents, a surrogate transition model, and simulation-level assumptions about aerodynamic interaction and charging strategy. That still makes it a very useful bridge between classical racing optimal control and strategic multi-agent RL.

## Pages Created From This Source

- [[a_competitor_aware_race_management_policy_a_game_theoretical_approach]]
- [[competitor_aware_race_management]]
