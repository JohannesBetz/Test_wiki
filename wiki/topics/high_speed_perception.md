---
tags: [topic]
date: 2026-05-06
sources: 1
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

## Representative Papers

- [[autonomous_vehicles_on_the_edge]]

## Open Problems

The survey argues that racing-specific high-speed perception remains thin. Open issues include long-range detection beyond 100 m, motion blur, sensor synchronization, robust camera/radar/LiDAR fusion, sparse racetrack landmarks, and lack of public high-speed racing perception datasets.
