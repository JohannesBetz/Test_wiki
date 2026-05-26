---
tags: [technique]
date: 2026-05-22
sources: 1
---

# Perceptive Nonlinear Model Predictive Control

## Definition

Perceptive nonlinear model-predictive control uses exteroceptive terrain information to modify the constraints and objectives of an online nonlinear MPC problem, so locomotion behavior can account for what the robot sees ahead rather than only what it has already contacted.

## Key Approaches

In [[perceptive_locomotion_through_nonlinear_model_predictive_control]], terrain perception is converted into local structure that an optimizer can actually use in real time: steppability classification, plane segmentation, and a signed distance field are extracted from a robot-centric elevation map and embedded as terrain-feasibility and collision-related constraints inside the MPC problem.

For this vault, the key point is that perception changes the feasible set of the controller, not merely its initialization or a downstream heuristic.

## Representative Papers

- [[perceptive_locomotion_through_nonlinear_model_predictive_control]]

## Open Problems

Perceptive NMPC inherits all the usual hard parts of nonlinear MPC, then adds another layer: the terrain description itself is partial, noisy, and computationally expensive. The central design challenge is how rich the perceptive terrain model can be before the controller loses the speed needed to stay useful online.
