---
tags: [paper]
date: 2026-05-13
task: autonomous_racing
venue: "IEEE Transactions on Field Robotics 2024"
sources: 1
year: "2024"
doi: "10.1109/TFR.2024.3501252"
topic:
  - autonomous_racing
  - autonomous_vehicle_racing
  - autonomous_racing_platforms
tech_backbone: []
tech_representation: []
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: [indy_autonomous_challenge]
models_used: [er_autopilot_1_1]
hardware_used: [cars_and_race_cars]
simulators_used: []
---

# er.autopilot 1.1: A Software Stack for Autonomous Racing on Oval and Road Course Tracks

> er.autopilot 1.1: A Software Stack for Autonomous Racing on Oval and Road Course Tracks | IEEE Transactions on Field Robotics 2024 | Ayoub Raji, Danilo Caporale, Francesco Gatti, Alessandro Toschi, Nicola Musiu, Micaela Verucchi, Francesco Prignoli, Davide Malatesta, André Fialho Jesus, Andrea Finazzi, Francesco Amerotti, Fabio Bagni, Eugenio Mascaro, Pietro Musso, and Marko Bertogna

## Summary

This paper documents a fielded full-stack autonomous racing system for the Indy Autonomous Challenge and related road-course competition settings.

Its central contribution is not one isolated planner or controller, but the integrated architecture required to race on both oval and road-course tracks, handle static obstacles, execute active overtakes, and sustain speeds above 75 m/s.

## Method

The paper presents `er.autopilot 1.1`, the software stack used by TII Unimore Racing, formerly TII EuroRacing.

The stack spans the whole classical autonomy pipeline:

- perception,
- localization,
- state estimation,
- planning,
- control,
- and simulation support.

Compared with the earlier version, the updated system adds LiDAR-based localization, lateral-velocity estimation, a radar-based local controller for safe pull-overs, and a refined vehicle model inside the MPC layer.

For this vault, that makes the paper a strong integration reference. It shows how a high-speed racecar stack evolves when the task shifts from predominantly oval racing to include a demanding road course like Monza.

## Key Results

The paper summarizes outcomes and lessons from the first two IAC seasons and reports that the team consistently achieved podium results.

The most important result for the vault is breadth: the stack is shown handling solo high-speed runs, obstacle avoidance, head-to-head passing, and road-course operation within one coherent system.

## Hardware Used

- [[cars_and_race_cars]]


## Related Work

This paper belongs directly near [[autonomous_racing_platforms]], [[indy_autonomous_challenge]], and [[autonomous_vehicle_racing]], because it is fundamentally a fielded competition-stack paper.

Compared with [[forzaeth_race_stack_scaled_autonomous_head_to_head_racing_on_fully_commercial_off_the_shelf_hardware]], the contrast is especially useful. ForzaETH emphasizes accessible reproducibility on 1:10 hardware, while `er.autopilot 1.1` represents a specialized full-size stack built for extreme speed and elite competition constraints.

It also pairs well with [[gripmap_an_efficient_spatially_resolved_constraint_framework_for_offline_and_online_trajectory_planning_in_autonomous_racing]], since both live in the IAC world where banked ovals, dust, overtaking geometry, and local grip variation become operationally decisive.

## Notes / Critique

The strongest value of this paper is systems honesty. It makes clear that winning-level autonomous racing depends on the orchestration of many modules, not just on one elegant planning or control algorithm.

It also expands the vault's view of modern autonomous racing from module papers toward operational software architecture, which is exactly what many surveys end up underspecifying.
