---
tags: [source]
date: 2026-05-08
sources: 1
---

# Kalaria Alpha Racer Source

> Source: `raw/pdfs/kalaria_Alpha_racer.pdf`
> Paper: α-RACER: Real-Time Algorithm for Game-Theoretic Motion Planning and Control in Autonomous Racing using Near-Potential Function, L4DC 2025

## Summary

This paper introduces `alpha-RACER`, a real-time game-theoretic framework for multi-car autonomous racing. The goal is not only to drive near the vehicle's limits, but also to perform competitive maneuvers such as overtaking and blocking against multiple other racecars.

The central claim is that autonomous racing needs a long-horizon interaction model: short-horizon local games and single-car racing-line tracking are not enough to capture real competitive racecraft.

## Method

The paper formulates racing as an infinite-horizon discounted dynamic game over multiple cars. Each agent uses an MPC controller, but the key policy variables are higher-level parameters that shape how the controller tracks a perturbed racing line.

Those parameters control aggressiveness, racing-line speed scaling, overtaking offsets, and blocking behavior. This creates a compact policy space rich enough to represent competitive maneuvering while still being tractable online.

To compute approximate Nash-equilibrium strategies in real time, the paper uses [[dynamic_near_potential_functions]]. The method learns a neural near-potential function offline from simulated races, then maximizes it online to pick the current policy parameters for the ego car.

## Evaluation

The paper evaluates the method in three-car racing scenarios. It reports a small approximation gap for the learned potential function, low Nash regret for the resulting online optimizer, and better race outcomes than several baselines.

The main baseline comparisons are against opponents with mismatched discount factors, opponents trained with less simulated data, iterated best response with short planning horizons, and self-play reinforcement learning.

## Notes / Critique

The strongest part of the paper is the combination of game-theoretic interaction structure and practical real-time control. It does not try to solve the full racing game from scratch online; instead, it compresses the strategic space into interpretable maneuver parameters and uses offline learning to make online equilibrium search cheap.

The main limitation is modeling bias. The success of the learned near-potential function depends on the chosen policy parametrization, simulated data distribution, and dynamic-game assumptions. If real races require richer maneuvers or denser traffic patterns, the compact parameter space may become restrictive.

## Pages Created From This Source

- [[alpha_racer_real_time_algorithm_for_game_theoretic_motion_planning_and_control_in_autonomous_racing_using_near_potential_function]]
- [[dynamic_near_potential_functions]]
