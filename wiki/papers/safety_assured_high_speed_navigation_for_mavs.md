---
tags: [paper]
date: 2026-05-08
task: robotics
venue: "Science Robotics"
sources: 1
year: "2025"
topic:
  - autonomous_drone_racing
  - Highly_dynamic_autonomous_system
tech_backbone: []
tech_representation: []
tech_generation: [safety_assured_high_speed_aerial_navigation]
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: [super]
simulators_used: []
---

# Safety-Assured High-Speed Navigation for MAVs

> Safety-Assured High-Speed Navigation for MAVs | Science Robotics 2025 | Yunfan Ren, Fangcheng Zhu, Guozheng Lu, Yixi Cai, Longji Yin, Fanze Kong, Jiarong Lin, Nan Chen, and Fu Zhang

## Summary

This paper tackles one of the sharpest problems in agile robotics: how to fly a compact micro air vehicle very fast in unknown clutter while still maintaining a principled notion of safety.

The central claim is that high speed and safety do not have to be traded in the crude way many previous systems assumed. With the right sensing stack, vehicle design, and planning architecture, a drone can stay both aggressive and safety-assured.

## Method

The paper introduces [[super]], a compact MAV with a 280 mm wheelbase, thrust-to-weight ratio above 5, and long-range 3D LIDAR sensing.

The key planning idea is [[safety_assured_high_speed_aerial_navigation]]. At each replanning cycle, the system computes:

- a safe trajectory constrained to known free space,
- and a faster trajectory that may extend into both known and unknown space.

This dual-trajectory strategy lets the robot preserve a fallback-safe option while still exploiting optimistic motion for speed.

The paper improves earlier versions of this idea in two important ways. First, it distinguishes known free space directly on LIDAR point clouds, which avoids the heavier occupancy-grid machinery used by prior work. Second, it uses a differentiable MINCO-style trajectory parameterization to reduce optimization cost and to optimize the switching time between the two trajectories.

## Key Results

In simulation, the paper reports that the planning framework reduces failure rates by 35.9 to 95.8 times relative to strong baseline methods while also flying faster.

In real-world tests, SUPER achieves autonomous flights above 20 m/s in unknown outdoor environments while maintaining a 100 percent success rate across eight trials with varying lighting conditions from daylight to full night.

The paper also demonstrates abilities that are especially relevant for real deployment:

- avoiding thin obstacles such as wires down to 2.5 mm,
- navigating through dense wooded clutter and narrow spaces,
- and supporting applied tasks such as target tracking, waypoint following, and autonomous exploration.

## Related Work

For this vault, the paper belongs close to [[Highly_dynamic_autonomous_system]] and [[autonomous_drone_racing]]. Compared with [[champion_level_drone_racing_using_deep_reinforcement_learning]], it is less about racing performance against a fixed course and more about safety-assured navigation in unknown environments.

It also connects naturally to [[high_speed_perception]], because the long-range 3D LIDAR is not just a sensor choice but part of what makes the safety guarantee practical at high speed.

Compared with racing papers that rely heavily on a known track or extensive offline learning, this work leans harder on onboard perception and online planning structure.

## Notes / Critique

The best part of the paper is that it makes the safety-speed tradeoff concrete and system-level. The vehicle design, sensor choice, and planner all clearly matter, and the results show the benefit of taking that coupling seriously.

The main caveat is scope. The system is impressive in unknown cluttered flight, but the paper says less about adversarial multi-agent interaction, opponent-aware tactics, or broader mission reasoning beyond reaching goals safely and quickly.
