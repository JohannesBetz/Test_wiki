---
tags: [technique]
date: 2026-05-26
sources: 1
---

# Actor-Critic Model Predictive Control

## Definition

Actor-Critic Model Predictive Control (`AC-MPC`) is a hybrid control technique that integrates differentiable model predictive control (MPC) as the parameterized actor within an actor-critic reinforcement learning (RL) framework. It combines the short-term trajectory planning and constraint satisfaction of MPC with the long-term task objective optimization of RL.

## Key Approaches

In [[actor_critic_model_predictive_control_differentiable_optimization_meets_reinforcement_learning_for_agile_flight]], `AC-MPC` is proposed for vision-based agile flight. The critic network learns the value function of state-action spaces, while the differentiable MPC actor optimizes the short-term trajectory based on cost weights updated via analytical policy gradients.

This technique addresses a central architectural debate in the vault:

**should high-speed control rely on the safety and structure of classical model-based MPC, or the task-level reward optimization and speed of model-free RL?**

AC-MPC shows that these paradigms can be unified mathematically through differentiable programming.

It belongs naturally near [[model_predictive_control]], [[reinforcement_learning]], and [[real_time_neural_mpc_deep_learning_model_predictive_control_for_quadrotors_and_agile_robotic_platforms]].

## Representative Papers

- [[actor_critic_model_predictive_control_differentiable_optimization_meets_reinforcement_learning_for_agile_flight]]

## Open Problems

Open problems include:
- **Computational Overhead**: Solving a differentiable MPC inside the RL loop in real time requires significant onboard computational resources.
- **Local Minima**: Differentiable optimization through non-convex MPC cost structures can get trapped in poor local optima.
- **Stability Guarantees**: Formal proof that the learned cost updates of the critic do not violate the safety constraints or stability proofs of the underlying MPC.
