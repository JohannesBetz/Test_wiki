---
tags: [paper]
date: 2026-05-13
task: autonomous_driving
venue: "manuscript / local PDF"
sources: 1
year: "2026"
topic:
  - cognitive_navigation
tech_backbone: [adversarial_theory_of_mind]
tech_representation: []
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
hardware_used: [cars_and_race_cars]
simulators_used: []
---

# Learning What They Pretend to Think: Adversarial ToM for Safety-Critical Driving Policies

> Learning What They Pretend to Think: Adversarial ToM for Safety-Critical Driving Policies

## Summary

This paper appears to ask a sharp multi-agent autonomy question: how should an autonomous driving policy behave when other agents are not merely dynamic obstacles, but strategic actors whose visible behavior may conceal or distort their true intent?

That framing is important for this vault because it pushes driving intelligence beyond geometric prediction and toward adversarial social reasoning.

## Method

The paper's central idea is best captured as [[adversarial_theory_of_mind]].

Within that framing, the policy does not rely only on raw future-state prediction. It tries to reason about another agent's latent intent or displayed belief state under interaction pressure, especially in scenarios where naive trust in observed behavior could produce unsafe decisions.

That makes the paper a natural neighbor to:

- [[neural_nonlinear_opinion_dynamics]], which also treats fast interaction choice as a structured decision problem,
- [[dynamic_near_potential_functions]], which also compresses strategic multi-agent reasoning into a more tractable policy mechanism,
- and the broader [[cognitive_navigation]] idea that perception, decision, and execution must stay tightly coupled in safety-critical autonomy.

## Key Result

The main result, at least at the level supported by the accessible local material, is not a racing-specific controller but a stronger argument that safe driving policies may need adversarial intent modeling in the loop.

In other words, this paper strengthens a broader claim in the wiki:

**competent high-consequence driving can depend on modeling what another agent is trying to make you believe, not only what that agent is physically doing.**

## Hardware Used

- [[cars_and_race_cars]]


## Related Work

This paper belongs closest to the behavioral-planning side of the vault rather than low-level control.

Compared with [[think_deep_and_fast_learning_neural_nonlinear_opinion_dynamics_from_inverse_dynamic_games_for_split_second_interactions]], it likely emphasizes adversarial intent modeling more directly than deadlock-free rapid commitment.

Compared with [[alpha_racer_real_time_algorithm_for_game_theoretic_motion_planning_and_control_in_autonomous_racing_using_near_potential_function]], it likely shifts the focus from approximate equilibrium computation toward theory-of-mind robustness in interactive driving.

Compared with end-to-end racing policies, it represents a more structured bet that explicit reasoning about other agents' hidden intent still matters.

## Notes / Critique

The strongest conceptual contribution is that it reframes driving interaction as a partially strategic epistemic problem, not only a trajectory-forecasting problem.

The main caveat is evidentiary: the local PDF text layer was not recoverable cleanly in this workspace, so this note is intentionally high level and should be revisited if a cleaner text source, DOI, or abstract becomes available.
