---
tags: [paper]
date: 2026-05-13
task: autonomous_racing
venue: "Proceedings of Machine Learning Research 2025 (CoRL 2024)"
sources: 1
year: "2025"
url: "https://proceedings.mlr.press/v270/djeumou25a.html"
topic:
  - autonomous_racing
  - autonomous_racing_control
  - motion_control
  - learning_based_control
  - autonomous_drifting
tech_backbone: [diffusion_models]
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

# One Model to Drift Them All: Physics-Informed Conditional Diffusion Model for Driving at the Limits

> One Model to Drift Them All: Physics-Informed Conditional Diffusion Model for Driving at the Limits | Proceedings of Machine Learning Research 2025 (CoRL 2024) | Franck Djeumou, Thomas Jonathan Lew, Nan Ding, Michael Thompson, Makoto Suminaka, Marcus Greiff, and John Subosits

## Summary

This paper asks whether one learned model can support reliable autonomous drifting across multiple cars and changing surface conditions instead of requiring a separately tuned expert model for each setup.

The answer is a structured one: learn a conditional diffusion model over the parameters of a physics-informed dynamics model, then use that model inside real-time [[model_predictive_control]] so the controller can adapt online while driving at the handling limit.

## Method

The paper begins from a real systems problem. At-limit driving is highly sensitive to uncertain and multimodal properties of the road, the vehicle, and their interaction. A single fixed dynamics model is therefore easy to break.

The proposed solution is to learn a conditional diffusion model from an unlabeled multimodal trajectory dataset. Rather than generating raw controls directly, the diffusion model captures a distribution over parameters of a physics-informed data-driven dynamics model.

That choice matters:

- it keeps the learned part grounded in vehicle-dynamics structure,
- it gives the system a way to represent multiple plausible dynamics regimes,
- and it fits naturally into an MPC loop where online measurements can condition which regime is currently relevant.

The result is not a pure end-to-end policy. It is a learned adaptation mechanism wrapped around a structured controller for limit handling.

## Key Results

The paper reports experiments on a Toyota Supra and a Lexus LC 500 under different tire and road conditions.

The main claim is strong and unusually relevant for this vault: a single shared diffusion model enables reliable autonomous drifting on both vehicles, matches the performance of task-specific expert models, and generalizes better to unseen conditions.

For racing research, that is the important shift. The contribution is not just "drifting works," but "cross-vehicle at-limit adaptation works without retraining a separate expert for each case."

## Hardware Used

- [[cars_and_race_cars]]


## Related Work

This paper belongs directly in [[autonomous_drifting]], where it reads like a newer generation of work compared with earlier controller-centric drifting papers such as [[a_controller_framework_for_autonomous_drifting_design_stability_and_experimental_validation]] and [[toward_automated_vehicle_control_beyond_the_stability_limits_drifting_along_a_general]].

It also belongs near [[model_predictive_control]], because the learned model is valuable precisely because it can be inserted into a real-time receding-horizon controller rather than only evaluated offline.

Compared with [[lipschitz_regularized_learned_dynamics_for_autonomous_racing_mpc]], the shared theme is controller-aware learned dynamics. The difference is emphasis: the Lipschitz paper focuses on model regularity for MPC compatibility, while this paper focuses on multimodal online adaptation across changing vehicles and surfaces.

Compared with [[deep_dynamics_vehicle_dynamics_modeling_with_a_physics_constrained_neural_network_for_autonomous_racing]], the overlap is again learned dynamics under physical structure. This paper goes further into multimodality and online inference under severe at-limit variation.

## Notes / Critique

The strongest idea is the representation choice. Diffusion is not used here as a fashionable generative layer pasted onto racing; it is used because the dynamics family is genuinely multimodal.

That makes the paper more interesting than a generic learned-dynamics result. It suggests that drifting control may be less about finding one best model and more about maintaining a useful distribution over possible models while the controller keeps working in real time.
