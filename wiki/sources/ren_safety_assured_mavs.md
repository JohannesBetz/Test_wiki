---
tags: [source]
date: 2026-05-08
sources: 1
---

# Ren Safety Assured MAVs Source

> Source: `raw/pdfs/Ren_safety_assured_MAVS.pdf`
> Paper: Safety-Assured High-Speed Navigation for MAVs, Science Robotics 2025

## Summary

This paper studies a hard version of agile autonomy: how a micro air vehicle can fly faster than 20 m/s through cluttered, previously unknown environments while retaining a meaningful safety guarantee.

The work is important for this vault because it addresses the same speed-versus-safety tension that appears in autonomous racing, but in an aerial robot that must react to occlusions, thin obstacles, narrow gaps, and severe sensing constraints.

## Method

The paper introduces `SUPER`, a compact micro air vehicle with high thrust-to-weight ratio, long-range 3D LIDAR sensing, and a planning stack designed specifically for safety-assured high-speed flight.

The planning framework generates two trajectories at each replanning cycle:

- one trajectory confined to known free space to preserve safety,
- and a second trajectory that uses both known and unknown space to maintain higher speed.

The system improves prior two-trajectory approaches by operating directly on point clouds rather than a heavier occupancy-grid representation and by using a more efficient differentiable trajectory parameterization. This reduces planning time while preserving the core safety structure.

## Evaluation

The paper reports extensive simulation and real-world testing. In simulation, the proposed framework reduces failure rates dramatically relative to strong baselines while also flying faster and planning roughly twice as fast.

In real-world field tests, SUPER reaches autonomous flight speeds above 20 m/s in unknown natural environments, avoids thin obstacles such as wires, navigates through narrow cluttered passages, and operates under large lighting variation including nighttime conditions.

## Notes / Critique

The strongest contribution is systems integration. The paper does not treat planning, sensing, and vehicle design as separable; the safety and speed results depend on all three working together.

The main limitation is that the safety guarantee is still tightly coupled to the onboard sensing and mapping assumptions. The system is far more deployment-ready than many agile-autonomy papers, but it is still not a general solution to all aerial interaction or multi-agent settings.

## Pages Created From This Source

- [[safety_assured_high_speed_navigation_for_mavs]]
- [[super]]
- [[safety_assured_high_speed_aerial_navigation]]
