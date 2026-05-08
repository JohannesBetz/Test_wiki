---
tags: [paper]
date: 2026-05-08
task: autonomous_racing
venue: "Proceedings of the 7th Annual Learning for Dynamics and Control Conference (PMLR 283)"
sources: 1
year: "2025"
url: "https://proceedings.mlr.press/v283/kalaria25a.html"
eprint: "2412.08855"
topic:
  - autonomous_racing
  - autonomous_racing_planning
  - autonomous_racing_control
tech_backbone: [model_predictive_control]
tech_representation: []
tech_generation: [dynamic_near_potential_functions]
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
simulators_used: []
---

# α-RACER: Real-Time Algorithm for Game-Theoretic Motion Planning and Control in Autonomous Racing using Near-Potential Function

> α-RACER: Real-Time Algorithm for Game-Theoretic Motion Planning and Control in Autonomous Racing using Near-Potential Function | L4DC 2025 | Dvij Kalaria, Chinmay Maheshwari, and Shankar Sastry

## Summary

This paper studies competitive multi-car racing as a dynamic game rather than as pure trajectory tracking or pure policy learning. The motivating problem is that a strong racing agent must reason about overtaking, blocking, and long-horizon positional advantage while still operating near dynamic limits in real time.

The authors propose `alpha-RACER`, which combines an interpretable MPC-based maneuver parametrization with an offline-learned near-potential function for fast online equilibrium search.

## Method

The racing interaction is modeled as an infinite-horizon discounted dynamic game over all cars. Each agent's low-level controller is MPC, but the strategic decision variable is not the raw control sequence. Instead, each agent chooses five policy parameters that shape a reference trajectory derived from the single-agent optimal raceline.

These parameters control:

- how aggressively the MPC tracks the reference,
- how strongly the reference follows the nominal raceline speed profile,
- and how the reference deforms for overtaking and blocking relative to the nearest front and rear competitors.

This gives a compact policy class that can express racing maneuvers while keeping the online optimization manageable.

The second key idea is [[dynamic_near_potential_functions]]. The paper learns a neural near-potential function offline from 4000 simulated three-car races. Online, the ego agent maximizes that learned potential at the current game state, and the resulting maximizer is used as an approximate Nash-equilibrium policy parameter.

## Key Results

The paper reports that the learned near-potential function approximates unilateral value changes well: on the training distribution, the relative approximation gap stays within 10 percent of the value-function range, with a median around 2 percent.

The resulting online optimizer also yields low Nash regret, reported within about 3 percent of the value-function range for the ego vehicle across race states.

In 99 three-car races, the method beats all tested baselines:

- against opponents trained with a lower discount factor, it wins 61 races;
- against opponents trained with a higher discount factor, it wins 52 races;
- against opponents trained with less data, it wins 76 races;
- against iterated best response opponents, it wins 73 races;
- against self-play RL opponents, it wins 91 races.

The strongest qualitative comparison is against short-horizon IBR: the paper argues that IBR can win local accelerations or straight-line moves but loses long-horizon track position because it does not preserve global raceline reasoning as effectively.

## Related Work

This paper belongs at the intersection of [[autonomous_racing_planning]] and [[autonomous_racing_control]]. Like other MPC-based racing work, it uses structured optimization and a vehicle model rather than an end-to-end learned policy. Unlike single-agent MPC papers, it treats overtaking and blocking as first-class strategic behavior.

It also sits near the game-theoretic interaction line already present in the vault, such as [[a_competitor_aware_race_management_policy_a_game_theoretical_approach]] and [[think_deep_and_fast_learning_neural_nonlinear_opinion_dynamics_from_inverse_dynamic_games_for_split_second_interactions]], but it differs from both. Compared with competitor-aware race management, it is shorter horizon and lower level. Compared with Neural NOD, it keeps the strategic interaction explicit through a compact equilibrium-search game model instead of learning an interaction abstraction from demonstrations.

## Notes / Critique

The best feature of the paper is the decomposition. By learning a potential-like surrogate of long-horizon game value changes, it avoids the usual trap of doing expensive equilibrium computation online at racing rates.

The main caveat is expressivity. The policy space is intentionally small and hand-designed around raceline perturbations, so the quality of the method depends on whether real competitive racing behavior can be captured well by those five maneuver parameters.
