---
tags: [technique]
date: 2026-05-08
sources: 1
---

# Safety-Assured High-Speed Aerial Navigation

## Definition

Safety-assured high-speed aerial navigation is an approach to agile MAV autonomy in which the vehicle flies near its dynamic limits while maintaining an explicit fallback-safe trajectory confined to known free space.

The point is to keep a meaningful safety guarantee without collapsing into overly conservative slow flight.

## Key Approach

[[safety_assured_high_speed_navigation_for_mavs]] implements this idea with a dual-trajectory planning scheme:

- a guaranteed-safe trajectory in known free space,
- and a faster trajectory that may use both known and unknown space.

This is paired with long-range 3D LIDAR perception, point-cloud-based free-space reasoning, and efficient differentiable trajectory optimization so the strategy can run onboard at high replanning rates.

## Relationship to Highly Dynamic Autonomy

This technique belongs naturally inside [[Highly_dynamic_autonomous_system]] and is adjacent to [[autonomous_drone_racing]].

Compared with aggressive racing-style methods that assume a known course, it focuses more directly on uncertainty and safety in unknown environments. Compared with conservative safe-navigation methods, it tries harder to exploit the vehicle's full agility.

## Representative Papers

- [[safety_assured_high_speed_navigation_for_mavs]]

## Open Problems

Open problems include scaling the method to denser multi-agent airspace, handling stronger sensing degradation, and integrating richer task objectives without eroding the safety-speed balance that makes the approach attractive.
