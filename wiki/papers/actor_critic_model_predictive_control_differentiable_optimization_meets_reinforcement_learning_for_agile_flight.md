---
tags: [paper]
date: 2026-05-26
task: Highly_dynamic_autonomous_system
venue: "IEEE Transactions on Robotics 2025"
sources: 1
year: "2025"
topic:
  - autonomous_drone_racing
  - control
tech_backbone: [reinforcement_learning]
tech_representation: [model_predictive_control]
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
hardware_used: [drones]
simulators_used: []
doi: ""
---

# Actor-Critic Model Predictive Control: Differentiable Optimization meets Reinforcement Learning for Agile Flight

> Actor-Critic Model Predictive Control: Differentiable Optimization meets Reinforcement Learning for Agile Flight | IEEE Transactions on Robotics 2025 / ICRA 2024 | Angel Romero, Elie Aljalbout, Yunlong Song, and Davide Scaramuzza

## Summary

This paper introduces **Actor-Critic Model Predictive Control**, a framework designed to combine the advantages of model-free reinforcement learning (RL) and model predictive control (MPC). By embedding a differentiable MPC directly as the policy actor within an actor-critic RL loop, the method unifies short-term predictive planning (MPC) with long-term cost value estimation (RL critic).

## Method

The framework is trained using [[reinforcement_learning]] and [[model_predictive_control]]:
- **Differentiable MPC Actor**: An MPC controller is embedded in the network whose cost weights and parameters are updated using analytical policy gradients backpropagated through the optimizer.
- **RL Critic**: A neural network critic estimates the value function of states, providing the long-term task objective directly to the MPC cost formulation.
- **Unifying Strengths**: Unifies model-free task-level reward flexibility with model-based safety/constraint satisfaction.

## Key Results

- Evaluated in simulation and real-world quadcopter flights for high-speed waypoint navigation and racing.
- Outperformed classical model-free RL in sample efficiency and robustness against dynamic changes (out-of-distribution environments).
- Retained the safety constraints of MPC while achieving superhuman racing speeds up to **21 m/s**.

## Hardware Used

- [[drones]] (Agilicious platform)

## Funding / Grants

- Supported by the European Research Council (ERC) Consolidator Grant [[agileflight]].

## Related Work

This paper addresses the core control design question raised in [[ Highly_dynamic_autonomous_system|Highly Dynamic Autonomous Systems]]: how to balance learned control policies with model-based predictive optimization.

It directly connects to:
- [[real_time_neural_mpc_deep_learning_model_predictive_control_for_quadrotors_and_agile_robotic_platforms]], which distills MPC into a neural controller, whereas Actor-Critic MPC directly optimizes the MPC cost via differentiable programming.
- [[hybrid_internal_model_learning_agile_legged_locomotion_with_simulated_robot_response]], which uses implicit modeling, while this paper focuses on explicit optimization-bound hybrid control.

## Notes / Critique

By making the MPC solver differentiable, the authors show that learning can improve model-based controllers online without stripping away their safety guarantees. This represents a major paradigm shift toward hybrid control systems.
