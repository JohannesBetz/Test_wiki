---
tags: [source]
date: 2026-05-27
sources: 1
---

# Jia Autonomous Racing With Dynamic Games Source

> Source: `raw/pdfs/Jia_Autonomous_Racing_With_Dynamic_Games.pdf`
> Paper: Autonomous Racing With Dynamic Games

## Summary

This source introduces a game-theoretic autonomous racing planner built around `dynamic potential games` and a scalable online planner called `RAPID`.

For this vault, the paper matters because it sits in a very specific niche of the racing-planning branch:

- not pure MPC tracking,
- not pure end-to-end RL,
- and not only offline game surrogates,

but a more explicit online dynamic-game view of competitive racing interaction.

## Method / Framing

The PDF structure is unusually informative even though the embedded bibliographic metadata is sparse. The core sections are:

- `Problem Formulation`
- `Dynamic Potential Games`
- `RAPID: Scalable Planner for Racing`
- `Simulation Results`
- `Hardware Experiments`

That is enough to place the paper reliably. The central idea appears to be that multi-agent racing can be formulated as a dynamic game whose structure is made more tractable through a potential-game-style reformulation and then executed with a scalable racing planner.

## Relevance

This source is especially relevant to:

- [[autonomous_racing_planning]]
- [[dynamic_potential_games]]
- [[dynamic_near_potential_functions]]

It is also a useful bridge between older game-theoretic racing work and newer approximations such as [[dynamic_near_potential_functions]] and [[learned_model_predictive_game]].

## Notes / Critique

The main strength of this source is architectural clarity: it treats competitive racing as a genuinely strategic multi-agent problem.

The main limitation is that the local PDF does not expose a clean citation header in the text layer, so this ingest is written conservatively as a method-level placement rather than a benchmark-heavy deep parse.

## Pages Created From This Source

- [[autonomous_racing_with_dynamic_games]]
- [[dynamic_potential_games]]
