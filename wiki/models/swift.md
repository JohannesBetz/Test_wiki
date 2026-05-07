---
tags: [model]
date: 2026-05-07
sources: 1
---

# Swift

## Definition

Swift is the autonomous drone-racing system introduced in [[champion_level_drone_racing_using_deep_reinforcement_learning]]. It combines onboard perception, visual-inertial state estimation, gate-based localization, and a reinforcement-learning control policy to race FPV drones at champion level.

## Key Approaches

- Onboard-only deployment with camera, IMU/VIO, and Jetson TX2 compute.
- Gate-corner detection using a U-Net-style network.
- Gate-based pose correction fused with [[visual_inertial_odometry]] using a Kalman filter.
- Control policy trained with [[proximal_policy_optimization]].
- [[empirical_residual_modeling]] for observation and dynamics errors to improve [[sim_to_real_transfer]].

## Representative Papers

- [[champion_level_drone_racing_using_deep_reinforcement_learning]]

## Open Problems

Swift is not opponent-aware, not trained for crash recovery, and depends on visual/environmental consistency with training data. Future extensions would need opponent modeling, adaptive race strategy, robust appearance generalization, and recovery behavior.
