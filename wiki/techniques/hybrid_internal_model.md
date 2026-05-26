---
tags: [technique]
date: 2026-05-26
sources: 2
---

# Hybrid Internal Model

## Definition

Hybrid Internal Model (`HIM`) is a learned locomotion-control technique in which the controller estimates both explicit motion state and an implicit disturbance-relevant response from the robot's own history, rather than relying on a detailed explicit model of the environment.

## Key Approaches

In [[hybrid_internal_model_learning_agile_legged_locomotion_with_simulated_robot_response]], the controller uses proprioceptive sensing and IMU data to build a latent internal response representation. The policy then uses that representation together with explicit velocity estimates to infer disturbances from the environment and maintain robust locomotion.

In [[learning_humanoid_locomotion_with_perceptive_internal_model]], this technique is directly extended into the [[perceptive_internal_model]] by concatenating exteroceptive elevation maps with proprioceptive history to perform joint velocity and state estimation for humanoid locomotion.

This matters for the vault because it offers a distinct answer to a recurring question in highly dynamic robotics:

**should robustness come mainly from richer terrain perception, explicit adaptation modules, or a stronger learned internal response model?**

`HIM` is one of the clearest examples of the third path.

It belongs naturally near [[reinforcement_learning]], [[sim_to_real_transfer]], and [[quadrupedal_locomotion]].

## Representative Papers

- [[hybrid_internal_model_learning_agile_legged_locomotion_with_simulated_robot_response]]
- [[learning_humanoid_locomotion_with_perceptive_internal_model]]

## Open Problems

Open problems include how interpretable the implicit response embedding really is, how well the technique transfers across bodies and sensing setups, and how far internal-response modeling can go before richer exteroceptive perception becomes unavoidable.
