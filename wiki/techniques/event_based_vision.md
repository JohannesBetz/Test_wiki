---
tags: [technique]
date: 2026-05-07
sources: 1
---

# Event-Based Vision

## Definition

Event-based vision uses sensors that asynchronously report brightness changes rather than full image frames. This can reduce latency and motion blur for fast-moving objects.

## Key Approaches

In [[outplaying_elite_table_tennis_players_with_an_autonomous_robot]], event-based vision is used for high-speed ball spin estimation. Ace's gaze-control systems track the ball with event cameras, pan/tilt mirrors, and tunable lenses. The system estimates angular velocity using both a low-latency CNN path and a higher-accuracy contrast-maximization path.

## Representative Papers

- [[event_based_vision_a_survey]]
- [[outplaying_elite_table_tennis_players_with_an_autonomous_robot]]

## Open Problems

For highly dynamic autonomy, event-based vision is promising when frame cameras suffer from motion blur or latency, but it still requires careful tracking, calibration, fusion, and task-specific estimation pipelines.
