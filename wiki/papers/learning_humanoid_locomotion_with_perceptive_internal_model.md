---
tags: [paper]
date: 2026-05-26
task: robotics
venue: "arXiv 2024"
sources: 1
year: "2024"
url: "https://arxiv.org/abs/2411.14386"
topic:
  - Highly_dynamic_autonomous_system
  - embodied_autonomous_intelligence
  - real_world_robotic_reinforcement_learning
tech_backbone: [reinforcement_learning]
tech_representation: [sim_to_real_transfer, exteroceptive_sensing]
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: [pim]
hardware_used: [humanoids]
simulators_used: []
---

# Learning Humanoid Locomotion with Perceptive Internal Model

> Learning Humanoid Locomotion with Perceptive Internal Model | arXiv 2024 | Junfeng Long, Junli Ren, Moji Shi, Zirui Wang, Tao Huang, Ping Luo, and Jiangmiao Pang | URL: https://arxiv.org/abs/2411.14386

## Summary

This paper introduces the **Perceptive Internal Model (PIM)**, a framework designed to tackle the unstable morphology and high degrees of freedom in humanoid locomotion. Incorporating exteroceptive sensing usually introduces noise and high computational rendering cost in simulation. PIM resolves this by using an onboard, robot-centered elevation map directly in the state prediction loop. This enables zero-shot sim-to-real transfer and fast 3-hour training on a single RTX 4090 GPU.

## Method

The framework is trained using [[reinforcement_learning]] (PPO).

The central contribution is [[pim]], which concatenates current perceptive height grid observations $o^p_t$ with proprioceptive history $o^n_{t-H:t}$ to perform joint state prediction:
- Builds upon the [[hybrid_internal_model]] (HIM) state prediction architecture.
- Predicts linear velocity $\hat{v}_{t+1}$ and latent next-step proprioceptive state $l_t$ using self-supervised contrastive learning.
- **Symmetry Regularization**: gait-symmetry transformations applied to observations and actions across the sagittal ($x\text{-}z$) plane to improve stability and alignment.
- **Action Curriculum**: arm and waist joints are initially locked to zero range and relaxed as training proceeds.
- **Elevation Map Module**: queries 96 points in a $0.8\text{m} \times 1.2\text{m}$ grid centered around the base link. During inference, this map is generated from a Mid-360 LiDAR or RGB-D camera.

## Key Results

- **Continuous Stair Climbing**: Over 90% success rate traversing stairs of $\ge 0.15\text{m}$ height. This is a significant improvement over previous blind or two-stage approaches (which maxed out at $10\text{cm}$ or required costly hardware-noise simulation).
- **Extreme Terrain Navigation**: Traverses wooden platforms of $\ge 0.4\text{m}$, gaps, and slopes of $15^\circ$.
- **Training Efficiency**: The entire policy trains in under 3 hours on an RTX 4090 GPU in simulation.
- **Sim-to-Real Deployment**: Successful zero-shot transfer onto the **Unitree H1** and **Fourier GR-1** humanoid robots.

## Hardware Used

- [[humanoids]] (Unitree H1 and Fourier GR-1)

## Related Work

This paper directly extends [[hybrid_internal_model_learning_agile_legged_locomotion_with_simulated_robot_response]], showing that exteroceptive height maps can be integrated directly into the predictor to resolve the sim-to-real gap for complex terrains.

It belongs near:
- [[real_world_humanoid_locomotion_with_reinforcement_learning]], which focuses on zero-shot real-world humanoid locomotion but lacks exteroceptive step alignment.
- [[humanoid_parkour_learning]], which handles extreme parkour terrains but struggles with fine-grained footholds like continuous stairs.
- [[beamdojo_learning_agile_humanoid_locomotion_on_sparse_footholds]], which utilizes LiDAR elevation mapping for sparse foothold planning, whereas PIM integrates the perception directly into the state predictor.

## Notes / Critique

The primary strength of PIM is its simplicity and computational efficiency. Directly querying terrain heights in simulation bypasses the need for rendering depth maps or dealing with raw point clouds, resolving the domain gap issues and memory bottleneck.

The cross-platform validation on Fourier GR-1 and Unitree H1 is notable. H1 has a single tandem ankle joint, while GR-1 has parallel ankle joints with 2DoF. PIM successfully runs on both, proving its robustness to joint topology variations.
