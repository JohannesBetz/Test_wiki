---
tags: [topic]
date: 2026-05-06
sources: 3
---

# High Speed Perception

## Definition

High-speed perception covers mapping, localization, object detection, free-space detection, and state estimation when an autonomous system moves fast enough that sensing range, latency, motion blur, synchronization, and sparse landmarks directly constrain safety and performance.

## Key Approaches

In [[autonomous_vehicles_on_the_edge]], autonomous racing perception includes:

- SLAM and mapping, including LiDAR-based racetrack mapping.
- Localization with AMCL, EKF, GraphSLAM, NDT, Kalman filters, LiDAR, odometry, GPS, and vehicle sensors.
- Cone/object detection for [[formula_student_driverless]] using camera-based deep detectors such as YOLO variants and SSD MobileNet.
- Free-space detection with semantic segmentation.
- LiDAR distortion compensation for high-speed operation.

In [[champion_level_drone_racing_using_deep_reinforcement_learning]], high-speed perception appears in an aerial setting: [[visual_inertial_odometry]] drifts under aggressive flight and motion blur, so gate detections are used as landmarks and fused with VIO through a Kalman filter.

In [[outplaying_elite_table_tennis_players_with_an_autonomous_robot]], high-speed perception appears in table tennis: APS cameras localize a fast ball in 3D, while [[event_based_vision]] estimates spin at low latency for high-speed, high-spin returns.

## Representative Papers

- [[autonomous_vehicles_on_the_edge]]
- [[champion_level_drone_racing_using_deep_reinforcement_learning]]
- [[outplaying_elite_table_tennis_players_with_an_autonomous_robot]]

## Open Problems

The survey argues that racing-specific high-speed perception remains thin. Open issues include long-range detection beyond 100 m, motion blur, sensor synchronization, robust camera/radar/LiDAR fusion, sparse racetrack landmarks, and lack of public high-speed racing perception datasets.

Swift adds an appearance-generalization caution: a perception stack can be fast enough for champion-level racing but still brittle when illumination or visual conditions differ from training.
