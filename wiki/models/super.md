---
tags: [model]
date: 2026-05-08
sources: 1
---

# SUPER

## Definition

SUPER is the safety-assured high-speed aerial robot introduced in [[safety_assured_high_speed_navigation_for_mavs]]. It is a compact micro air vehicle designed for fast autonomous flight in unknown cluttered environments.

## Key Approaches

- Compact airframe with a 280 mm wheelbase and thrust-to-weight ratio above 5.
- Lightweight long-range 3D LIDAR sensing for obstacle detection in clutter and under low light.
- [[safety_assured_high_speed_aerial_navigation]] with dual trajectories: one safe in known free space and one faster trajectory that can exploit unknown space.
- Point-cloud-based free-space reasoning to reduce mapping cost relative to occupancy-grid methods.
- Efficient differentiable trajectory optimization for fast replanning onboard.

## Representative Papers

- [[safety_assured_high_speed_navigation_for_mavs]]

## Open Problems

SUPER is built for single-robot high-speed navigation in unknown environments. Future extensions would need richer multi-agent interaction, broader mission reasoning, and continued robustness under sensing degradation or extreme environmental change.
