---
tags: [technique]
date: 2026-05-22
sources: 1
---

# Rapid Motor Adaptation

## Definition

Rapid Motor Adaptation (`RMA`) is a learned control architecture in which a base locomotion policy is paired with an online adaptation module that infers latent environment or dynamics conditions from recent experience.

## Key Approaches

In [[rma_rapid_motor_adaptation_for_legged_robots]], the adaptation module predicts a latent variable from recent motion history, and that latent conditions the locomotion controller. The goal is to let the robot respond quickly to terrain changes, payload shifts, wear, or other hidden dynamics changes without requiring explicit terrain labels or hand-written regime switching.

This makes `RMA` especially important for this vault because it turns adaptation itself into a learned component of the control loop rather than only a property of offline training.

It also sits naturally between [[reinforcement_learning]], [[sim_to_real_transfer]], and [[era_of_experience]].

## Representative Papers

- [[rma_rapid_motor_adaptation_for_legged_robots]]

## Open Problems

Open problems include how interpretable the latent adaptation state really is, how stable the adaptation remains under severe distribution shift, and how well the architecture transfers across different robot bodies and control objectives.
