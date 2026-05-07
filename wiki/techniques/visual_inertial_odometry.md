---
tags: [technique]
date: 2026-05-07
sources: 1
---

# Visual-Inertial Odometry

## Definition

Visual-inertial odometry estimates a robot's motion by combining camera measurements with inertial measurements from an IMU.

## Key Approaches

In [[champion_level_drone_racing_using_deep_reinforcement_learning]], VIO provides high-rate onboard state estimates for [[swift]]. Because high-speed drone racing causes drift and motion blur, gate detections are used as landmarks. Relative gate poses are estimated and fused with VIO through a Kalman filter to correct translational drift.

## Representative Papers

- [[champion_level_drone_racing_using_deep_reinforcement_learning]]

## Open Problems

At high speed, VIO must handle motion blur, feature loss, latency, rapid rotations, and drift over short but aggressive trajectories. Racing settings are useful because small errors can immediately affect gate clearance and crash risk.
