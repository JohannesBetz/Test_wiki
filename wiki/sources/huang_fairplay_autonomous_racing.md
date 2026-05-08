---
tags: [source]
date: 2026-05-08
sources: 1
---

# Huang Fair Play Autonomous Racing Source

> Source: `raw/pdfs/Huang_FairPlay_Autonomous_Racing.pdf`
> Paper: Fair Play in the Fast Lane: Integrating Sportsmanship into Autonomous Racing Systems

## Summary

This paper studies how autonomous racing systems can behave competitively without violating human sportsmanship norms. Instead of treating fair racing as a side effect of reward tuning or post hoc filtering, the paper makes sportsmanship an explicit part of the interaction-planning problem.

The motivating claim is that human racing includes rules and conventions such as the one-motion rule and enough-space rule, and autonomous systems should reason about those constraints directly when choosing overtaking and defensive actions.

## Method

The paper proposes a bi-level game-theoretic framework for versus racing under sportsmanship principles (`SPS`).

At the higher level, the system uses a discrete Stackelberg game solved with Monte Carlo Tree Search (`MCTS`) to choose strategic racing intentions.

At the lower level, the resulting multi-vehicle interaction is realized through a generalized Nash equilibrium formulation that computes dynamically feasible trajectories while respecting the selected sportsmanship-aware strategic constraints.

## Evaluation

The reported evaluation focuses on two-car racing scenarios such as straightaways and corners, with agents that may or may not know and follow the encoded sportsmanship rules.

The paper reports metrics around overtaking success, violation frequency, and time efficiency, using these experiments to show how explicit sportsmanship modeling changes racing outcomes and interaction quality.

## Notes / Critique

The main strength is conceptual clarity. Rather than hiding etiquette inside reward weights, the paper makes fairness and racecraft explicit in the decision structure.

The main limitation is scope. The framework looks well matched to focused two-agent interaction settings, but it is less clear how gracefully it scales to denser fields, partial observability, or real-time full-stack deployment.

## Pages Created From This Source

- [[fair_play_in_the_fast_lane_integrating_sportsmanship_into_autonomous_racing_systems]]
- [[sportsmanship_aware_racing_strategy]]
