---
tags: [paper]
date: 2026-05-26
task: Highly_dynamic_autonomous_system
venue: "arXiv 2026"
sources: 1
year: "2026"
topic:
  - autonomous_drone_racing
  - control
tech_backbone: [reinforcement_learning]
tech_representation: [sim_to_real_transfer]
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
hardware_used: [drones]
simulators_used: []
doi: ""
---

# Learning Agile Quadrotor Flight in the Real World

> Learning Agile Quadrotor Flight in the Real World | arXiv 2026 | Yunfan Ren, Zhiyuan Zhu, Jiaxu Xing, and Davide Scaramuzza

## Summary

This paper presents a self-adaptive control framework that learns agile quadrotor flight directly in the real world. By eliminating the need for precise system identification or offline sim-to-real transfer, the proposed method utilizes online residual learning and differentiable simulation to adapt policies during actual flight.

## Method

The framework utilizes [[differentiable_simulation]] and [[reinforcement_learning]]:
- **Online Residual Learning**: Augments a simple nominal dynamics model with a neural network that estimates unmodeled aerodynamic disturbances (such as blade-element drag and wind) in real time.
- **Adaptive Temporal Scaling (ATS)**: Automatically scales the temporal constraints of the trajectory during flight to safely explore the physical limits of the quadrotor.
- **Real-world Anchored Short-horizon Backpropagation Through Time (RASH-BPTT)**: A sample-efficient, online gradient-based policy update method that updates the control policy in flight using the learned hybrid model.

## Key Results

- Zero-shot real-world policy evolution: successfully adapts a conservative base policy (peak speed of $1.9\text{ m/s}$) to an agile, high-performance policy (peak speed of **$7.3\text{ m/s}$**) within **100 seconds** of total flight time.
- Operates reliably near actuator saturation limits.
- Robust under external disturbances and changes in dynamics (e.g. payload modifications) without offline retraining.

## Hardware Used

- [[drones]] (Agilicious platform)

## Funding / Grants

- Supported by the European Research Council (ERC) Consolidator Grant [[agileflight]].

## Related Work

This paper shifts the paradigm of sim-to-real transfer by executing the adaptation step entirely online in the real world:
- It complements *Learning on the Fly: Rapid Policy Adaptation via Differentiable Simulation*, which also utilizes differentiable simulation.
- It addresses the online-adaptation bottlenecks discussed in [[rma_rapid_motor_adaptation_for_legged_robots|RMA]] and [[hybrid_internal_model_learning_agile_legged_locomotion_with_simulated_robot_response|HIM]] but in a high-speed quadrotor domain.

## Notes / Critique

Online policy updates under hardware safety constraints are notoriously difficult. RASH-BPTT solves this by anchoring backpropagation to short trajectories, preventing gradient explosion. The 100-second convergence time represents a highly practical solution to real-world drone adaptation.
