---
tags: [paper]
date: 2026-05-13
task: robotics
venue: "IEEE Robotics and Automation Letters 2023"
sources: 1
year: "2023"
doi: "10.1109/LRA.2023.3246839"
topic:
  - Highly_dynamic_autonomous_system
  - autonomous_drone_racing
  - control
tech_backbone: [cnn]
tech_representation: [neural_mpc]
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
hardware_used: [drones]
simulators_used: []
---

# Real-Time Neural MPC: Deep Learning Model Predictive Control for Quadrotors and Agile Robotic Platforms

> Real-Time Neural MPC: Deep Learning Model Predictive Control for Quadrotors and Agile Robotic Platforms | IEEE Robotics and Automation Letters 2023 | Tim Salzmann, Elia Kaufmann, Jon Arrizabalaga, Marco Pavone, Davide Scaramuzza, and Markus Ryll

## Summary

This paper asks how the benefits of model predictive control can be preserved when raw optimization time is too costly for very agile robotic systems.

Its answer is Neural MPC: a learned controller that approximates the behavior of an MPC expert closely enough to retain strong control performance while running much faster at deployment time.

## Method

The paper targets quadrotors and other agile robotic platforms, where the control loop must operate at high rate and where aggressive maneuvers make latency especially expensive.

The basic strategy is to learn the control policy from MPC behavior rather than derive every control command from online optimization at runtime.

That places the method in a useful middle ground:

- more structured than a generic learned controller trained only from task reward,
- but much cheaper online than solving full MPC repeatedly on hardware.

For this vault, the key idea is control distillation for agility: use classical optimal-control structure offline, then deploy a neural controller that inherits much of that behavior at real-time speed.

## Key Results

The paper is framed around quadrotors and agile robotic platforms, which makes the result especially relevant to high-speed flight.

For this vault, the most important result is architectural rather than domain-specific: the paper shows one practical route for reconciling MPC-quality behavior with the timing constraints of agile deployment.

That makes it a strong adjacent reference for autonomous drone racing and other high-dynamics control tasks, even though it is not itself a racing study.

## Hardware Used

- [[drones]]


## Related Work

This paper belongs near [[model_predictive_control]], because it keeps MPC as the source of control intelligence even while replacing the expensive online solve with a learned surrogate.

It also connects naturally to [[Highly_dynamic_autonomous_system]] and [[autonomous_drone_racing]], where controller latency is often one of the invisible but decisive factors separating elegant algorithms from actually fast physical behavior.

Compared with [[champion_level_drone_racing_using_deep_reinforcement_learning]], this work is less about sim-to-real reinforcement learning and more about compressing a structured optimal-control policy into a neural runtime controller.

Compared with [[lipschitz_regularized_learned_dynamics_for_autonomous_racing_mpc]], the overlap is again control-aware learning, but the emphasis is different: the Lipschitz paper regularizes a learned prediction model for MPC, while this paper distills the MPC controller itself into a neural policy.

## Notes / Critique

The strongest contribution is making the latency-performance tradeoff concrete. For agile systems, controller runtime is part of the dynamics problem, not just an implementation detail.

The main limitation for this vault is transfer specificity. The paper is broad on agile robotics and quadrotors, but it does not directly answer racing-specific interaction, opponent-awareness, or track-constrained planning questions.
