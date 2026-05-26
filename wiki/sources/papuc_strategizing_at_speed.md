---
tags: [source]
date: 2026-05-20
sources: 1
---

# Papuc Strategizing at Speed Source

> Source: `raw/pdfs/Papuc_Strategizing_at_Speed.pdf`
> Paper: Strategizing at Speed: A Learned Model Predictive Game for Multi-Agent Drone Racing, arXiv 2026

## Summary

This paper studies multi-agent drone racing through a game-theoretic planning lens. The title already gives the core structure: a learned model predictive game is used so fast drones can race not only aggressively, but strategically, against other moving agents.

That makes it an important addition to the vault because it extends the drone-racing branch from:

- solo high-speed control,
- and multi-agent RL coordination,

into explicit short-horizon tactical reasoning under interaction.

## Method

The central technique is best represented here as [[learned_model_predictive_game]].

The title suggests a hybrid design:

- `model predictive` structure for short-horizon planning and replanning,
- `game` structure for strategic interaction among racing agents,
- and a `learned` component that likely makes the game or prediction model fast enough for real-time drone-racing use.

This places the paper between fully explicit game-theoretic planning and end-to-end multi-agent learning.

## Evaluation

At the vault level, the core evaluation question is whether learned model-predictive-game reasoning improves multi-agent tactical behavior in drone racing compared with methods that are only reactive, only time-optimal, or only learned.

That makes it a useful complement to both coordination-focused and pursuit-evasion-style drone papers already in the vault.

## Notes / Critique

The most interesting conceptual contribution is that it treats drone-racing strategy as a real-time game rather than as a pure trajectory-generation or policy-learning problem.

The metadata was clean enough to recover canonical title, authors, and arXiv DOI. I did not have a clean full-text extraction path in this workspace, so this source note stays careful and method-level rather than pretending to reconstruct every experiment.

## Pages Created From This Source

- [[strategizing_at_speed_a_learned_model_predictive_game_for_multi_agent_drone_racing]]
- [[learned_model_predictive_game]]
