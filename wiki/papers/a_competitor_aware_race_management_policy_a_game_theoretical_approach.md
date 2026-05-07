---
tags: [paper]
date: 2026-05-07
task: autonomous_racing
venue: "TU/e MSc Thesis"
sources: 1
year: "2026"
url: "https://research.tue.nl/en/studentTheses/4d1f7178-d6e5-4da8-92d9-368629d1233b"
topic:
  - autonomous_racing
  - autonomous_racing_planning
tech_backbone: [reinforcement_learning]
tech_representation: []
tech_generation: [competitor_aware_race_management]
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
simulators_used: []
---

# A Competitor-aware Race Management Policy: A Game Theoretical Approach

> A Competitor-aware Race Management Policy: A Game Theoretical Approach | TU/e MSc Thesis | Wytze de Vries

## Summary

This thesis formulates electric autonomous endurance racing as a multi-agent race-management problem where finishing position matters more than local lap-time optimality. The central idea is that battery usage, slipstream exploitation, overtaking, and pit decisions must be optimized jointly over the full race horizon, because the best single-lap policy may lose the race.

The paper is a useful complement to the rest of the vault because it shifts the racing objective from near-limit control toward long-horizon strategy under interaction and energy constraints.

## Method

The method is a bi-level framework for [[competitor_aware_race_management]].

At the lower level, the thesis solves a single-lap multi-agent game-theoretic optimal-control problem. The model includes ribbon-track vehicle dynamics, load-sensitive tire grip, powertrain losses, aerodynamic drag/downforce interaction between nearby cars, and asymmetric collision-avoidance constraints inspired by motorsport racing rules.

That lower-level game is then approximated with a neural surrogate that predicts how the inter-car time gap evolves from one lap to the next as a function of both agents' energy allocation. This surrogate becomes the environment for an upper-level reinforcement-learning problem.

At the upper level, RL learns race-long strategic decisions: how much battery energy to spend per lap, whether to pit, and how much energy to charge. The objective is to finish ahead of the competitor, not merely to minimize aggregate lap time.

## Key Results

The framework is demonstrated on a two-agent, 45-lap electric endurance race. The thesis reports that aerodynamic interactions, especially slipstream-based energy saving, are decisive for the race outcome.

The most important result is qualitative but strong: strategies optimized for finishing position differ fundamentally from single-agent minimum-time strategies. An agent may intentionally accept slower local laps if that preserves energy, improves race-end positioning, or creates a better overtaking window later.

The thesis also argues that purely short-horizon competitive planners are too limited for this setting because battery and charging decisions span the full race horizon. That motivates the upper-level RL policy over the learned surrogate race model.

## Related Work

This thesis overlaps with several existing threads in the vault. It is strategy-oriented like [[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]], but GT Sophy learns tactical racecraft directly in simulation, whereas this work builds a structured race-level decision layer on top of a game-theoretic single-lap model.

It also complements [[game_theoretic_motion_planning_for_multi_robot_racing]] and other game-theoretic racing work by moving from short-horizon motion interaction toward race-long energy and pit strategy.

Finally, it connects naturally to [[energy_management_strategy_for_an_autonomous_electric_racecar_using_optimal_control]], but adds explicit competitor interaction and race-position objectives rather than treating energy management as a single-car optimization problem.

## Notes / Critique

The strongest idea here is the decomposition. The thesis uses optimization where local physics and interaction structure matter most, then uses RL where long-horizon strategic reasoning and stochasticity matter more.

Its biggest limitation is external scope: only two agents are considered, and the whole framework depends on the fidelity of the lower-level interaction model and surrogate transition map. Still, it is one of the clearest examples in the vault of autonomous racing as race strategy rather than only control.
