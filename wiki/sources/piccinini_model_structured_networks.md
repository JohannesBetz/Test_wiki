---
tags: [source]
date: 2026-05-07
sources: 1
---

# Piccinini Model-Structured Networks Source

> Source: `raw/pdfs/Piccinini_Model-structured-Networks.pdf`
> Paper: Model-Structured Neural Networks to Control the Steering Dynamics of Autonomous Race Cars, arXiv:2507.20427

## Summary

This paper proposes [[model_structured_neural_networks]] for steering control in autonomous racing, with a specific controller called `MS-NN-steer`. The central idea is to embed prior knowledge about nonlinear vehicle dynamics directly into the neural architecture instead of relying on a purely black-box network.

The paper is useful for this vault because it pushes the control side of autonomous racing toward more interpretable learning-based methods. Rather than replacing the whole racing stack end to end, it targets one hard control subproblem: feedforward steering for full-scale race cars operating near the handling limit.

## Method

The proposed `MS-NN-steer` extends an earlier model-structured architecture by explicitly modeling how vehicle speed affects steering characteristics and the handling diagram. It is used as the feedforward steering block inside the TUM Autonomous Motorsport planning-and-control stack, where a Tube-MPC planner generates maneuvers and lower-level controllers execute them.

The paper compares `MS-NN-steer` against three benchmarks:

- The steering controller used by the winning A2RL 2024 team.
- A general-purpose neural network (`G-NN`).
- A prior model-structured baseline (`MS-NN-base`).

The authors also release open-source code for generating and tuning customized model-structured neural architectures.

## Evaluation

The controller is trained and validated on real telemetry from the 2024 [[abu_dhabi_autonomous_racing_league|A2RL]] competition using a full-scale autonomous race car. The paper emphasizes three properties:

- Better generalization than a general-purpose neural network when training data is reduced.
- Better accuracy than both the A2RL baseline controller and the earlier `MS-NN-base`.
- Much lower sensitivity to random weight initialization and learning-rate choice.

One concrete result is especially informative: with the smallest training-set configuration discussed in the paper, the validation RMSE of the general-purpose network rises to 0.327 deg, while `MS-NN-steer` achieves 0.097 deg. The paper also reports lower mean, variance, and peak steering errors than the benchmarks.

## Notes / Critique

The strongest part is the use of real full-scale racing data rather than only simulation. That makes the claim about generalization and data efficiency much more relevant for autonomous racing teams that cannot cheaply collect massive datasets.

The main caveat is scope. The paper focuses on feedforward steering control, not the full closed-loop racing problem, so its benefits still depend on the surrounding planner, feedback controller, and vehicle platform.

## Pages Created From This Source

- [[model_structured_neural_networks_to_control_the_steering_dynamics_of_autonomous_race_cars]]
- [[model_structured_neural_networks]]
