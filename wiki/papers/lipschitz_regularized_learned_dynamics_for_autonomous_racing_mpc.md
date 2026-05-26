---
tags: [paper]
date: 2026-05-13
task: autonomous_racing
venue: "RA-L preprint 2026"
sources: 1
year: "2026"
topic:
  - autonomous_racing
  - autonomous_racing_control
  - motion_control
  - learning_based_control
tech_backbone: []
tech_representation: [lipschitz_regularized_learned_dynamics]
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

# Lipschitz-Regularized Learned Dynamics for Autonomous Racing MPC

> Lipschitz-Regularized Learned Dynamics for Autonomous Racing MPC | RA-L preprint 2026

## Summary

This paper studies a familiar racing-control tension: learned dynamics models can improve prediction fidelity for MPC, but if the learned model is not sufficiently smooth or well behaved, the controller may become numerically fragile or overly sensitive near the limit.

The paper's answer is to regularize the learned dynamics model through a Lipschitz-oriented constraint so that it remains expressive while better aligned with the needs of downstream MPC.

## Method

The core object is a learned vehicle-dynamics model used inside an MPC racing controller.

The paper's distinctive move is to make regularity first-class. Rather than optimizing only predictive fit, it appears to penalize or constrain the model so that local changes in state and input do not produce uncontrolled sensitivity in the predicted dynamics.

For autonomous racing, this is attractive because MPC depends on repeated short-horizon prediction under rapidly changing lateral and longitudinal load conditions. A learned model that is too noisy or sharp may be accurate offline yet still make the optimizer harder to trust online.

## Key Results

The available local metadata supports a strong placement claim even though it does not expose the full paper text cleanly: this work belongs to the growing category of control-aware learned dynamics for racing.

For this vault, the most important contribution is therefore structural. The paper sharpens the question of what makes a learned model useful inside MPC, beyond raw one-step prediction accuracy.

## Hardware Used

- [[cars_and_race_cars]]


## Related Work

This paper belongs near [[model_predictive_control]], because the learned model is not the end product on its own; it is valuable insofar as it improves closed-loop receding-horizon control.

It also connects naturally to [[model_structured_neural_networks_to_control_the_steering_dynamics_of_autonomous_race_cars]], although the emphasis is different. The steering-network paper builds structure into a controller architecture, while this paper appears to build regularity into the learned prediction model that an MPC controller depends on.

Compared with [[kineto_dynamical_planning_and_accurate_execution_of_minimum_time_maneuvers_on_three_dimensional_circuits]], the overlap is in learned reduced-order dynamics for control, but this paper seems more focused on regularization and controller compatibility than on 3D minimum-time planning specifically.

## Notes / Critique

The strongest idea here is the control-theoretic instinct: a dynamics model for racing should not be judged only by fit quality, but also by whether it behaves in ways MPC can exploit reliably in real time.

The main limitation of this note is evidentiary. The local PDF metadata exposed the title and theme clearly, but not the full experimental detail, so this page should be treated as a careful high-level placement until a cleaner text extraction is available.
