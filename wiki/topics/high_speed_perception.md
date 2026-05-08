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

In [[safety_assured_high_speed_navigation_for_mavs]], high-speed perception appears in a different aerial form: long-range 3D LIDAR is used not only for obstacle detection but also to distinguish known free space directly on point clouds, which is what makes [[safety_assured_high_speed_aerial_navigation]] practical at speeds above 20 m/s.

[[autonomous_drone_racing_a_survey]] broadens the aerial perspective by showing how camera models, IMU calibration, motion blur, dynamic range, and sensor placement interact with planning and control at racing speeds, not only with perception in isolation.

[[racevla_vla_based_racing_drone_navigation_with_human_like_behaviour]] adds a multimodal variant: FPV perception is no longer only an input to explicit estimation modules, but part of a [[vision_language_action_models|language-conditioned policy]] that must convert visual context into control under tight timing constraints.

## Representative Papers

- [[autonomous_vehicles_on_the_edge]]
- [[champion_level_drone_racing_using_deep_reinforcement_learning]]
- [[outplaying_elite_table_tennis_players_with_an_autonomous_robot]]
- [[a_champion_level_vision_based_reinforcement_learning_agent_for_competitive_racing_in_gran_turismo_7]]
- [[safety_assured_high_speed_navigation_for_mavs]]
- [[autonomous_drone_racing_a_survey]]
- [[racevla_vla_based_racing_drone_navigation_with_human_like_behaviour]]

## Open Problems

The survey argues that racing-specific high-speed perception remains thin. Open issues include long-range detection beyond 100 m, motion blur, sensor synchronization, robust camera/radar/LiDAR fusion, sparse racetrack landmarks, and lack of public high-speed racing perception datasets.

Swift adds an appearance-generalization caution: a perception stack can be fast enough for champion-level racing but still brittle when illumination or visual conditions differ from training.

Vision-based GT7 racing adds an occlusion-memory challenge: perception may be local and incomplete, so competitive behavior depends on remembering track and opponent context rather than only reading the current frame.

SUPER adds a long-range obstacle-resolution challenge: at high speed, even small objects such as wires become mission-critical, so perception systems need both sufficient range and enough spatial fidelity to keep safety guarantees meaningful.

The ADR survey adds a sensor-stack realism challenge: high-speed flight pushes not just algorithms but the calibration, latency, and physical placement of sensors, so perception quality can degrade for reasons that are partly hardware and partly algorithmic.

RaceVLA adds a grounding challenge: once perception is folded into a large multimodal action model, it becomes harder to separate whether failures come from sensing, language conditioning, latent world modeling, or action decoding.
