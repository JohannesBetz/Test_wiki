---
tags: [paper]
date: 2026-05-07
task: autonomous_racing
venue: "arXiv"
sources: 1
year: "2025"
eprint: "2507.20427"
url: "https://arxiv.org/abs/2507.20427"
topic:
  - autonomous_racing
  - autonomous_racing_control
  - learning_based_control
tech_backbone: []
tech_representation: []
tech_generation: [model_structured_neural_networks]
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: [abu_dhabi_autonomous_racing_league]
models_used: []
simulators_used: []
---

# Model-Structured Neural Networks to Control the Steering Dynamics of Autonomous Race Cars

> Model-Structured Neural Networks to Control the Steering Dynamics of Autonomous Race Cars | arXiv:2507.20427 | Piccinini, Mungiello, Jank, Rosati Papini, Biral, and Betz

## Summary

This paper introduces `MS-NN-steer`, a steering controller based on [[model_structured_neural_networks]] for full-scale autonomous race cars. Instead of using a generic neural network, the method builds prior vehicle-dynamics knowledge into the controller architecture so that the learned model stays more interpretable, data-efficient, and robust.

The paper frames this as an autonomous-racing safety problem. Pure black-box networks can model steering behavior well on training data, but they are harder to trust near the handling limit where controller failures are expensive. The proposed architecture tries to keep the flexibility of learned models while preserving some of the structure of known vehicle dynamics.

## Method

`MS-NN-steer` is a feedforward steering controller embedded in the TUM Autonomous Motorsport planning-and-control stack. The surrounding system uses Tube-MPC for maneuver planning and then applies steering and longitudinal control for execution.

The paper extends a previous model-structured baseline by explicitly modeling how longitudinal speed changes the steering characteristics. This matters in racing because steering response and feasible handling change significantly with speed, especially near the limit.

The method is compared against three benchmarks:

- The A2RL-winning steering controller.
- A general-purpose neural network (`G-NN`).
- The earlier `MS-NN-base` architecture.

Beyond headline accuracy, the paper also studies how performance changes when the training set is reduced and when the random initialization or learning rate varies.

## Key Results

Using real telemetry from the 2024 [[abu_dhabi_autonomous_racing_league|A2RL]] competition, the paper reports that `MS-NN-steer` outperforms all three benchmarks.

The clearest generalization result appears when training data is reduced. On the smallest training-set setting reported in the paper, the validation RMSE of the general-purpose neural network rises to 0.327 deg, while `MS-NN-steer` reaches 0.097 deg. The earlier `MS-NN-base` sits between them at 0.115 deg.

The error-distribution analysis shows that `MS-NN-steer` has lower mean, variance, and peak steering errors than the benchmarks on both training and validation data. The initialization study also shows that its RMSE varies much less across random seeds than the general-purpose neural network, indicating a more stable training process.

The paper argues that this is practically important for racing teams: collecting full-scale data is expensive, and a controller that still generalizes under smaller datasets and lighter hyperparameter tuning is much easier to deploy.

## Related Work

This paper fits squarely into [[autonomous_racing_control]] and complements the more planning-focused work in this vault. It addresses how a planned trajectory is executed accurately through steering, rather than how the trajectory itself is generated.

It also continues a line of physics-aware learned vehicle models and controllers. In spirit, it is compatible with planning systems such as [[kineto_dynamical_planning_and_accurate_execution_of_minimum_time_maneuvers_on_three_dimensional_circuits]] and [[challenging_f1_drivers_in_physical_race_cars_with_human_inspired_online_learning]], where execution quality strongly affects whether aggressive plans remain feasible on real cars.

## Notes / Critique

The main strength is the use of real full-scale racing telemetry instead of only simulated data. That makes the generalization and data-efficiency claims feel much more credible.

A natural limitation is that the paper isolates one controller block. It does not yet show a full closed-loop race-performance gain from swapping in `MS-NN-steer`, although the authors identify deployment on the real A2RL car and tighter integration with planners as future work.
