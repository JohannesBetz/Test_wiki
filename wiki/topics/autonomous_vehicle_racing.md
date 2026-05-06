---
tags: [topic]
date: 2026-05-06
sources: 1
---

# Autonomous Vehicle Racing

## Definition

Autonomous vehicle racing studies autonomous racecars operating near the limits of handling, where high speed, high acceleration, low reaction time, uncertain sensing, nonlinear tire dynamics, and adversarial interaction become first-order problems.

In [[autonomous_vehicles_on_the_edge]], the scope is restricted to four-wheeled racecars and racecar-like platforms, including small-scale vehicles, full-size racecars, and racing simulators.

## Key Approaches

- Classical autonomy pipeline: [[high_speed_perception]] -> [[autonomous_racing_planning]] -> [[autonomous_racing_control]].
- Optimization and optimal-control approaches for raceline generation and minimum-lap-time objectives.
- [[model_predictive_control]] for local planning, tracking, robustness, and operation near dynamic limits.
- Learning-based control, especially repeated-lap learning and model-error compensation.
- [[end_to_end_autonomous_racing]] using deep learning and [[reinforcement_learning]].
- Platform-driven evaluation through [[f1tenth]], [[formula_student_driverless]], [[roborace]], [[indy_autonomous_challenge]], and simulation.

## Representative Papers

- [[autonomous_vehicles_on_the_edge]]

## Open Problems

- High-speed perception and sensor fusion.
- Multi-vehicle trajectory planning.
- Multi-agent prediction and interaction.
- Adversarial driving and risk-aware behavior.
- Real-time vehicle dynamics modeling.
- Balancing safety and lap-time performance.
- Common autonomous racing rules and regulations.
- Real-time full-stack software performance.
- Racing-specific sensors, compute, and high-speed hardware.
