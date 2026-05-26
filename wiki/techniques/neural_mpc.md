---
tags: [technique]
date: 2026-05-13
sources: 1
---

# Neural MPC

## Definition

Neural MPC is a control approach that uses a learned neural policy to approximate the behavior of a model predictive controller so that deployment can run much faster than repeated online optimization.

## Key Approach

[[real_time_neural_mpc_deep_learning_model_predictive_control_for_quadrotors_and_agile_robotic_platforms]] applies this idea to quadrotors and agile robotic systems.

The core idea is to keep MPC as the source of structured control behavior while distilling that behavior into a neural controller that can execute at real-time rates suitable for aggressive motion.

This is especially attractive when online MPC is accurate enough in principle but too computationally heavy for the reaction rates the platform requires.

## Relationship to MPC and Agile Control

This technique belongs near [[model_predictive_control]], [[Highly_dynamic_autonomous_system]], and [[autonomous_drone_racing]].

Compared with classical MPC, Neural MPC trades exact online optimization for speed. Compared with generic learned policies, it keeps a stronger connection to structured control design by learning from an MPC teacher.

## Representative Papers

- [[real_time_neural_mpc_deep_learning_model_predictive_control_for_quadrotors_and_agile_robotic_platforms]]

## Open Problems

Open problems include how faithfully the neural policy reproduces MPC behavior outside the training distribution, how safety or stability guarantees degrade under approximation, and whether the same distillation idea scales to richer multi-agent or racing-specific control tasks.
