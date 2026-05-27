---
tags: [source]
date: 2026-05-27
sources: 1
---

# Geles Superhuman Safe Agile Racing Source

> Source: `raw/pdfs/Geles_Superhuman_safe_agile_Flight.pdf`
> Paper: Superhuman Safe and Agile Racing through Multi-Agent Reinforcement Learning

## Summary

This source presents a multi-agent reinforcement-learning approach to drone racing that explicitly emphasizes three goals at once:

- `superhuman` performance,
- `safety`,
- and `agility`.

That makes it a strong fit for the vault. It extends the autonomous-drone-racing branch beyond the original Swift milestone by asking not only whether a single drone can fly fast, but whether safe aggressive racing can emerge through multi-agent learning.

## Method / Framing

The paper is best understood as a next-step RL racing paper in the AGILEFLIGHT / RPG line.

The title and reference structure make its role clear:

- it uses [[reinforcement_learning]] in a multi-agent setting,
- it targets competitive drone racing rather than solo navigation,
- and it explicitly frames safety as part of the objective rather than as a separate post hoc wrapper.

For the vault, that makes it a useful bridge between:

- [[champion_level_drone_racing_using_deep_reinforcement_learning]],
- [[dashing_for_the_golden_snitch_multi_drone_time_optimal_motion_planning_with_multi_agent_reinforcement_learning]],
- and the broader question of how multi-agent competitive behavior can remain fast without becoming reckless.

## Relevance

This source is especially relevant to:

- [[autonomous_drone_racing]]
- [[reinforcement_learning]]
- [[Highly_dynamic_autonomous_system]]

It also reinforces the AGILEFLIGHT branch, where several recent drone papers are starting to move from solo fast flight toward interaction-aware and competition-aware learning.

## Notes / Critique

The most attractive thing about this source is that it tries to hold `speed`, `competition`, and `safety` together.

The main caution is that multi-agent RL often inherits instability, opponent non-stationarity, and evaluation fragility. So any `superhuman` claim here should be read as highly impressive, but still dependent on the exact training distribution and race setup.

## Pages Created From This Source

- [[superhuman_safe_and_agile_racing_through_multi_agent_reinforcement_learning]]
