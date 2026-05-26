---
tags: [paper]
date: 2026-05-13
task: autonomous_racing
venue: "IEEE Robotics and Automation Letters 2024"
sources: 1
year: "2024"
doi: "10.1109/LRA.2024.3388847"
topic:
  - autonomous_racing
  - autonomous_racing_control
  - learning_based_control
tech_backbone: [cnn]
tech_representation: [physics_constrained_vehicle_dynamics_networks]
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

# Deep Dynamics: Vehicle Dynamics Modeling With a Physics-Constrained Neural Network for Autonomous Racing

> Deep Dynamics: Vehicle Dynamics Modeling With a Physics-Constrained Neural Network for Autonomous Racing | IEEE Robotics and Automation Letters 2024 | John Chrosniak, Jingyun Ning, and Madhur Behl

## Summary

This paper proposes a physics-constrained neural network for vehicle-dynamics modeling in autonomous racing.

The core motivation is that racing systems need models that are expressive enough to capture nonlinear vehicle behavior near the limit, but structured enough to remain useful for control and planning. A purely analytical model may be too crude; a purely black-box network may be too unconstrained.

## Method

The method learns vehicle dynamics with a neural network while embedding physical constraints into the modeling process.

That makes the model a hybrid object:

- more flexible than a hand-derived low-order dynamics approximation,
- but more structured than a generic function approximator trained only for predictive accuracy.

For racing, this matters because the model is not just an offline prediction artifact. Its behavior influences whether planning and control layers can trust the predicted responses near aggressive operating points.

## Key Results

The strongest result for this vault is architectural. The paper reinforces the idea that learned vehicle models for racing should be shaped by physical priors rather than judged only by prediction metrics.

That places it in the same broad family as other physics-aware and structure-aware racing works, while focusing specifically on the vehicle-dynamics-modeling layer rather than only on the controller or planner.

## Hardware Used

- [[cars_and_race_cars]]


## Related Work

This paper belongs near [[model_structured_neural_networks_to_control_the_steering_dynamics_of_autonomous_race_cars]], though the target is different. The steering-network paper builds structure into a controller, while this paper builds structure into the vehicle dynamics model itself.

It also connects naturally to [[kineto_dynamical_planning_and_accurate_execution_of_minimum_time_maneuvers_on_three_dimensional_circuits]], where learned reduced-order dynamics are used inside a planning-and-control loop.

Compared with [[lipschitz_regularized_learned_dynamics_for_autonomous_racing_mpc]], the overlap is again learned dynamics for control, but the emphasis here is physics-constrained model structure rather than regularity of the learned model for MPC compatibility.

## Notes / Critique

The strongest idea is the middle-ground modeling strategy. Racing is exactly the kind of domain where physics priors and learned flexibility should probably meet rather than compete.

The main limitation of this note is that the local PDF extraction gave clear metadata but not a clean abstract-level text dump, so this page is a reliable placement summary more than a fully reconstructed experimental deep read.
