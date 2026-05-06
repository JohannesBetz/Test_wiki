---
tags: [topic]
date: 2026-05-06
sources: 1
---

# Autonomous Racing Control

## Definition

Autonomous racing control turns a reference trajectory into steering, throttle, and braking commands while minimizing lateral error, heading error, and velocity error near the limits of tire and vehicle stability.

## Key Approaches

[[autonomous_vehicles_on_the_edge]] groups control into:

- Classical control: lookahead control, feedforward/feedback steering, G-G-diagram-aware controllers, slip-angle-based control, torque vectoring, and nonlinear longitudinal control.
- [[model_predictive_control]]: MPPI, SRMPC, NMPC, LPV-MPC, tube MPC, envelope control, and mixed-integer formulations.
- Learning-based control: iterative learning control, learning MPC, Gaussian-process model-error learning, adaptive MPC, DNN-assisted control, and online scaling/correction.
- Drifting control: controllers for stable operation beyond normal handling limits at high sideslip angles.

## Representative Papers

- [[autonomous_vehicles_on_the_edge]]

## Open Problems

The central problems are high-accuracy path/heading/velocity tracking, stable behavior under high lateral and longitudinal acceleration, real-time nonlinear modeling, and control policies that adapt to changing tires, friction, aerodynamics, and track conditions.
