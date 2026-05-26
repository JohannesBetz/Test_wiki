---
tags: [technique]
date: 2026-05-26
sources: 2
---

# Differentiable Simulation

## Definition

Differentiable Simulation is a policy-learning and optimization technique where the physics engine or dynamics simulator is fully differentiable. This allows exact analytical gradients of the loss function (e.g. trajectory tracking error) to be backpropagated directly through the dynamics model to update control policy parameters, offering vastly superior sample efficiency compared to model-free reinforcement learning.

## Key Approaches

In *Learning Quadrotor Control From Visual Features Using Differentiable Simulation*, differentiable simulation is used to train vision-based quadrotor control policies. Analytical gradients computed via a surrogate dynamics model allow the policy to learn recovery behaviors in seconds (from states) or minutes (from visual features), bypassing the sample-inefficiency of model-free RL.

In *Learning on the Fly: Rapid Policy Adaptation via Differentiable Simulation*, this technique is combined with online residual dynamics learning to adjust policies to wind and payload changes within 5 seconds of real-world flight.

In [[learning_agile_quadrotor_flight_in_the_real_world]], the framework uses Real-world Anchored Short-horizon Backpropagation Through Time (RASH-BPTT) in a differentiable simulator framework to enable robust online, in-flight policy updates.

It belongs naturally near [[reinforcement_learning]], [[model_predictive_control]], and [[sim_to_real_transfer]].

## Representative Papers

- *Learning Quadrotor Control From Visual Features Using Differentiable Simulation*
- *Learning on the Fly: Rapid Policy Adaptation via Differentiable Simulation*
- [[learning_agile_quadrotor_flight_in_the_real_world]]

## Open Problems

Open problems include:
- Gradient explosion or vanishing gradients when backpropagating through long time horizons (RASH-BPTT addresses this by using short horizons, but long-term planning remains difficult).
- The "reality gap" of the simulator's derivatives: if the simulator's gradients do not match the real-world gradients, the policy updates can destabilize the physical hardware.
- High computational complexity of representing complex contact forces (e.g. in legged parkour or racing collisions) in a differentiable format.
