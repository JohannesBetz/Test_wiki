---
tags: [technique]
date: 2026-05-26
sources: 1
---

# Perceptive Internal Model

## Definition

Perceptive Internal Model (`PIM`) is a legged locomotion state estimation and control technique that extends the [[hybrid_internal_model]] by directly concatenating current exteroceptive terrain observations (e.g. elevation maps) with proprioceptive history to predict the robot's future states.

## Key Approaches

In [[learning_humanoid_locomotion_with_perceptive_internal_model]], `PIM` uses a robot-centered elevation map (96 points queried in a $0.8\text{m} \times 1.2\text{m}$ grid) concatenated with proprioceptive observations. The state predictor estimates linear velocity $\hat{v}_{t+1}$ and next-step latent proprioceptive state $l_t$. 

This technique addresses a central problem in perceptive locomotion:

**How to integrate exteroceptive inputs without introducing massive simulator rendering cost, domain gap discrepancies, or noise from sensor movement.**

By bypassing depth image rendering and instead predicting next-step states from height maps, PIM minimizes computational overhead, enabling single-stage RL training to complete in under 3 hours on a single GPU.

It belongs naturally near [[hybrid_internal_model]], [[perceptive_locomotion]], and [[sim_to_real_transfer]].

## Representative Papers

- [[learning_humanoid_locomotion_with_perceptive_internal_model]]

## Open Problems

Open problems include:
- How to extend PIM to highly dynamic running/jumping maneuvers where elevation maps are updated under significant motion blur or sensor occlusion.
- How to align the elevation map frame under rapid orientation changes where gravity vector approximation drifts.
- Generalization of the concatenated proprioceptive-perceptive latent space across highly varied legged morphologies (e.g., quadrupeds vs. humanoids).
