---
tags: [paper]
date: 2026-05-26
task: Highly_dynamic_autonomous_system
venue: "ICRA 2026"
sources: 1
year: "2026"
topic:
  - autonomous_drone_racing
  - high_speed_perception
  - end_to_end_learning
tech_backbone: [reinforcement_learning]
tech_representation: [exteroceptive_sensing]
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

# Dream to Fly: Model-Based Reinforcement Learning for Vision-Based Drone Flight

> Dream to Fly: Model-Based Reinforcement Learning for Vision-Based Drone Flight | IEEE International Conference on Robotics and Automation (ICRA) 2026 | Angel Romero, Ashwin Shenai, Ismail Geles, Elie Aljalbout, and Davide Scaramuzza

## Summary

This paper presents **Dream to Fly**, a framework that applies model-based reinforcement learning (MBRL) using world models to fly drones directly from pixels to control commands (collective thrust and body rates). Unlike previous model-free RL systems (such as Swift) that require complex, handcrafted state-estimation pipelines and specialized perception rewards, Dream to Fly trains policies end-to-end directly from raw visual observations.

## Method

The framework utilizes [[reinforcement_learning]]:
- **World Model Training**: Uses a latent world model to simulate future trajectories from raw pixel observations, allowing the policy to be optimized entirely in latent space.
- **End-to-End Control**: Maps raw camera pixels directly to low-level quadrotor control commands (avoiding the need for VIO, gate detection, or Kalman filtering).
- **Emergent Attention**: Eliminates the need for a perception-aware reward term. The end-to-end training naturally incentivizes the policy to guide the camera toward feature-rich areas to minimize dynamic uncertainty.

## Key Results

- Trait-efficient: MBRL policy trains successfully from scratch inside a racetrack using only onboard camera pixels.
- Successfully navigates challenging FPV racetracks with high agility.
- Outperforms standard model-free (PPO) baselines in sample efficiency and visual robustness.

## Hardware Used

- [[drones]] (Agilicious platform)

## Funding / Grants

- Supported by the European Research Council (ERC) Consolidator Grant [[agileflight]].

## Related Work

This paper marks a key shift from hybrid perception-control stacks to end-to-end world model policies:
- It directly addresses the visual tracking constraints analyzed in [[how_fast_is_too_fast_the_role_of_perception_latency_in_high]].
- It compares against model-free systems like [[champion_level_drone_racing_using_deep_reinforcement_learning|Swift]] by removing the explicit Kalman-filtering and gate-detection modules.
- It belongs near [[learning_visual_parkour_from_generated_images]] in its vision-first framing.

## Notes / Critique

Hand-crafting state estimators and gate abstractions is highly labor-intensive. By replacing them with a learned world model, the authors show that end-to-end control is possible even at the dynamic limits of drone flight. The emergence of gaze-like camera alignment behavior directly from task-level reward is a powerful validation of MBRL.
