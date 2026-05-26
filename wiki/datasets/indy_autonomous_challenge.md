---
tags: [dataset]
date: 2026-05-06
sources: 3
---

# Indy Autonomous Challenge

## Definition

The Indy Autonomous Challenge is a full-size autonomous racing competition using a standardized Indy Lights-based racecar.

## Key Approaches

[[autonomous_vehicles_on_the_edge]] describes the IAC platform as a high-speed racecar with camera, LiDAR, radar, RTK GPS, and high-performance compute, using ROS2 middleware and aiming at speeds near 290 km/h.

[[gripmap_an_efficient_spatially_resolved_constraint_framework_for_offline_and_online_trajectory_planning_in_autonomous_racing]] uses an IAC Las Vegas Motor Speedway spin-out as motivation for spatially resolved grip constraints. The case shows how a globally invariant vehicle model can overestimate grip during an outside overtake on a dusty banked turn.

[[er_autopilot_1_1_a_software_stack_for_autonomous_racing_on_oval_and_road_course_tracks]] adds a rare team-level systems account from the IAC ecosystem, covering oval events, static obstacle avoidance, head-to-head passing, and the later Monza road-course expansion.

## Papers Using This

- [[autonomous_vehicles_on_the_edge]]
- [[gripmap_an_efficient_spatially_resolved_constraint_framework_for_offline_and_online_trajectory_planning_in_autonomous_racing]]
- [[er_autopilot_1_1_a_software_stack_for_autonomous_racing_on_oval_and_road_course_tracks]]

## Notes

At the survey's cut-off, only a few IAC papers had appeared because the competition was new. This is an obvious target for post-survey updates.

`er.autopilot 1.1` is one of the clearest post-survey updates because it documents what a podium-level full-scale stack actually looked like once the competition matured across multiple event types.

For post-survey full-scale racing comparisons, [[abu_dhabi_autonomous_racing_league]] is a closely related newer benchmark environment.
