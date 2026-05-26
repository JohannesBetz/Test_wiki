---
tags: [source]
date: 2026-05-26
sources: 1
---

# Long Learning Humanoid Locomotion Source

> Source: `raw/pdfs/Long_Learning_Humanoid_Locomotion.pdf`
> Paper: Learning Humanoid Locomotion with Perceptive Internal Model, arXiv 2024

## Summary

This paper presents the **Perceptive Internal Model (PIM)**, a framework that enables stable and robust humanoid locomotion on challenging terrains (such as stairs, gaps, and high platforms) by integrating exteroceptive elevation maps with proprioceptive history for state estimation and policy training.

For this vault, the paper matters because it showcases how incorporating elevation maps directly into the state predictor (based on the Hybrid Internal Model) can bridge the sim-to-real gap, avoid depth map rendering computational overhead, and allow fast training on standard hardware.

## Method

The training backbone is [[reinforcement_learning]] using Proximal Policy Optimization (PPO).

The key contribution is the [[perceptive_internal_model]] (PIM), which concatenates current robot-centered elevation map observations $o^p_t$ with proprioceptive history $o^n_{t-H:t}$ to estimate linear velocity $\hat{v}_{t+1}$ and predict latent proprioceptive states $l_t$. It builds on the [[hybrid_internal_model]] (HIM) base.

Key optimizations include:
- **Symmetry Regularization**: gait-symmetry transformations applied to observations and actions across the sagittal ($x\text{-}z$) plane.
- **Action Curriculum**: locking waist and arm joints to zero and gradually increasing their ranges as training proceeds.
- **Humanoid Rewards**: feet lateral distance penalty to prevent leg crossing and feet ground parallel penalty to ensure correct alignment.

## Evaluation

The proposed system was verified in simulation and transferred zero-shot to physical humanoid hardware:
- **Unitree H1** (180 cm height, 47 kg weight, 4DoF arm, 1DoF waist, 5DoF leg)
- **Fourier GR-1** (165 cm height, 55 kg weight, 4DoF arm, 3DoF waist, 6DoF leg, parallel ankle joints)

The hardware experiments show traversal over:
- Stairs of $\ge 0.15\text{m}$ height (with a $30\text{cm}$ step width constraint matching the robot's foot length).
- Gaps and high platforms of $\ge 0.4\text{m}$.
- Slopes of $15^\circ$.
- Robustness across Mid-360 LiDAR and RealSense camera configurations.

PIM achieved higher training efficiency (training in under 3 hours on an RTX 4090 GPU) and lower velocity estimation error than HIM.

## Notes / Critique

The main contribution is showing that low-cost height-map querying (96 sampled height points in a $0.8\text{m} \times 1.2\text{m}$ grid) is sufficient to drive state prediction and foot placement without the rendering cost of depth maps in simulation. This drastically reduces the sim-to-real gap. 

The evaluation is exceptionally strong, validating on two humanoids with distinct joint configurations (Fourier GR-1 features parallel ankle joints, whereas H1 has standard tandem ankles).

## Pages Created From This Source

- [[learning_humanoid_locomotion_with_perceptive_internal_model]]
- [[perceptive_internal_model]]
- [[pim]]
