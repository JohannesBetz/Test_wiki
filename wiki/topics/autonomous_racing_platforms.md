---
tags: [topic]
date: 2026-05-06
sources: 2
---

# Autonomous Racing Platforms

## Definition

Autonomous racing platforms are the vehicles, competition environments, sensors, compute stacks, middleware, and simulation tools used to evaluate autonomous racing systems.

## Key Approaches

[[autonomous_vehicles_on_the_edge]] divides platforms into small-scale vehicles and real autonomous race vehicles.

Small-scale platforms include 1:43 ORCA cars, 1:10 vehicles such as [[f1tenth]], and 1:5 AutoRally. These platforms are cheaper, easier to operate, and useful for repeated testing, education, learning, and control experiments.

Full-size or competition platforms include [[formula_student_driverless]], [[roborace]], [[indy_autonomous_challenge]], and EV Grand Prix Autonomous. They expose stronger constraints from vehicle dynamics, sensor range, compute, vibration, safety procedures, and real racing speeds.

[[forzaeth_race_stack_scaled_autonomous_head_to_head_racing_on_fully_commercial_off_the_shelf_hardware]] adds a concrete modern small-scale systems reference: [[forzaeth_race_stack]] treats the full 1:10 racing stack itself as the contribution and emphasizes reproducibility with commercial off-the-shelf hardware.

[[er_autopilot_1_1_a_software_stack_for_autonomous_racing_on_oval_and_road_course_tracks]] adds the full-scale competition counterpart: [[er_autopilot_1_1]] is a fielded race stack for IAC-style oval events and Monza road-course operation, highlighting what changes when the same software architecture must support very high speeds, overtakes, obstacle handling, and track-shape diversity.

[[efficient_trajectory_optimization_for_autonomous_racing_via_formula_1_data_driven_initialization]] adds a cross-scale knowledge-transfer angle: instead of transferring a full control stack from full-size racing to 1:10 platforms, it asks whether expert full-scale driving data itself can serve as a useful optimization prior for scaled autonomous racing.

[[introducing_hypractive_hyprs_artificial_intelligence_for_autonomous_mobility]] adds a broader autonomous-mobility systems angle: not every relevant autonomy entry is a competition platform or academic stack, and some appear first as integrated product-style system presentations.

## Representative Papers

- [[autonomous_vehicles_on_the_edge]]
- [[forzaeth_race_stack_scaled_autonomous_head_to_head_racing_on_fully_commercial_off_the_shelf_hardware]]
- [[er_autopilot_1_1_a_software_stack_for_autonomous_racing_on_oval_and_road_course_tracks]]

## Open Problems

The survey argues that most platforms rely on standard consumer sensors and compute. A major gap is hardware designed specifically for autonomous racing: high-speed perception, high vibration/shock resistance, low-latency compute, and reliable operation under racing loads.

The ForzaETH result adds a platform-translation question: how much progress can be made by scaling access and reproducibility at 1:10, and where do the limits of that strategy appear when researchers try to transfer ideas to full-size cars?

The `er.autopilot 1.1` result adds a standardization question from the opposite direction: once stacks become competition-grade at full scale, how much of that software can be generalized beyond one team, one event family, or one vehicle integration?
