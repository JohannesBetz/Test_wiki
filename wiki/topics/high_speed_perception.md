---
tags: [topic]
date: 2026-05-06
sources: 4
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

In [[a_champion_level_vision_based_reinforcement_learning_agent_for_competitive_racing_in_gran_turismo_7]], high-speed perception is folded directly into a learned racing policy: egocentric camera input and onboard sensors must support competitive multi-agent driving without explicit global localization at inference time.

## Representative Papers

- [[autonomous_vehicles_on_the_edge]]
- [[champion_level_drone_racing_using_deep_reinforcement_learning]]
- [[outplaying_elite_table_tennis_players_with_an_autonomous_robot]]
- [[a_champion_level_vision_based_reinforcement_learning_agent_for_competitive_racing_in_gran_turismo_7]]

## Open Problems

The survey argues that racing-specific high-speed perception remains thin. Open issues include long-range detection beyond 100 m, motion blur, sensor synchronization, robust camera/radar/LiDAR fusion, sparse racetrack landmarks, and lack of public high-speed racing perception datasets.

Swift adds an appearance-generalization caution: a perception stack can be fast enough for champion-level racing but still brittle when illumination or visual conditions differ from training.

Vision-based GT7 racing adds an occlusion-memory challenge: perception may be local and incomplete, so competitive behavior depends on remembering track and opponent context rather than only reading the current frame.
