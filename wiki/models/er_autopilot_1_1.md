---
tags: [model]
date: 2026-05-13
sources: 1
---

# er.autopilot 1.1

## Definition

er.autopilot 1.1 is a full-scale autonomous racing software stack developed by TII Unimore Racing for oval and road-course competition in the Indy Autonomous Challenge ecosystem.

## Key Approaches

- Modular full-stack architecture covering perception, localization, state estimation, planning, control, and simulation.
- Designed to support static obstacle avoidance, active overtakes, and very high-speed operation above 75 m/s.
- Extended from oval-racing use to road-course operation, including Monza-style track geometry.
- Updated with LiDAR-based localization, lateral-velocity estimation, radar-based safe pull-over control, and refined vehicle modeling for MPC.

## Representative Papers

- [[er_autopilot_1_1_a_software_stack_for_autonomous_racing_on_oval_and_road_course_tracks]]

## Open Problems

Open problems include how transferable such highly specialized full-scale stacks are across tracks, rulesets, and vehicle platforms, and how much of their architecture can be simplified or standardized without losing top-end racing performance.
