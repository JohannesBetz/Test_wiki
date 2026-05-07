---
tags: [technique]
date: 2026-05-07
sources: 1
---

# Empirical Residual Modeling

## Definition

Empirical residual modeling learns the mismatch between a nominal model and real-world behavior, then uses that learned error model to improve simulation, prediction, or control.

## Key Approaches

[[champion_level_drone_racing_using_deep_reinforcement_learning]] uses two residual models:

- Observation residuals: Gaussian processes model VIO/perception errors by comparing onboard estimates with motion-capture ground truth.
- Dynamics residuals: k-nearest-neighbour regression models residual accelerations as a function of platform state and commanded thrust.

These models are added to simulation and used to fine-tune Swift's policy for real-world deployment.

## Representative Papers

- [[champion_level_drone_racing_using_deep_reinforcement_learning]]

## Open Problems

Residual models are powerful when real-world error modes are repeatable, but can overfit to track, lighting, platform, and sensor conditions. For broader deployment, residual modeling must be combined with robust perception and adaptation to unseen environments.
