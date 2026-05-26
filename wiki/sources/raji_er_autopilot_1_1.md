---
tags: [source]
date: 2026-05-13
sources: 1
---

# Raji er.autopilot 1.1 Source

> Source: `raw/pdfs/Ajoub_er.autopilot_1.1_A_Software_Stack_for_Autonomous_Racing_on_Oval_and_Road_Course_Tracks.pdf`
> Paper: er.autopilot 1.1: A Software Stack for Autonomous Racing on Oval and Road Course Tracks, IEEE Transactions on Field Robotics 2024

## Summary

This paper presents the full software architecture used by TII Unimore Racing for the Indy Autonomous Challenge across oval tracks and the later Monza road-course setting.

For this vault, the paper matters because it is a rare modern full-scale systems account rather than a single-module contribution. It covers the stack required for static obstacle avoidance, active overtaking, operation above 75 m/s, and adaptation from oval racing to more complex road-course geometry.

## Method

The paper describes `er.autopilot 1.1`, a complete autonomous racing stack spanning perception, localization, state estimation, planning, control, and simulation.

The metadata and abstract highlight several updates over the prior version:

- LiDAR-based localization,
- lateral velocity estimation,
- a radar-based local controller for safe pull-overs,
- and refined vehicle modeling for the model predictive controller.

This makes the paper especially useful as a systems-integration reference. Instead of isolating one algorithmic novelty, it shows how several modules are made to cooperate on a full-size racecar under competition constraints.

## Evaluation

The paper reports lessons and results from the first two IAC seasons, including oval-racing challenges and the 2023 Monza road-course time trial.

For this vault, the main evaluation significance is that the stack consistently achieved podium finishes while covering a broader task set than simple solo time trials.

## Notes / Critique

The strongest contribution is scope. Many autonomous-racing papers are excellent module papers; this one is a fielded stack paper that reveals what has to exist around the planner or controller for the whole racecar to perform.

It also gives the vault a much stronger full-scale counterpart to [[forzaeth_race_stack]]: reproducible small-scale systems and highly specialized full-scale competition stacks now sit side by side.

## Pages Created From This Source

- [[er_autopilot_1_1_a_software_stack_for_autonomous_racing_on_oval_and_road_course_tracks]]
- [[er_autopilot_1_1]]
