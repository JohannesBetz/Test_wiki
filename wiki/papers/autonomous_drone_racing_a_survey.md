---
tags: [paper]
date: 2026-05-08
task: robotics
venue: "IEEE Transactions on Robotics"
sources: 1
year: "2024"
doi: "10.1109/TRO.2024.3400838"
topic:
  - autonomous_drone_racing
  - Highly_dynamic_autonomous_system
tech_backbone: [reinforcement_learning]
tech_representation: [visual_inertial_odometry]
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
hardware_used: [drones]
simulators_used: []
---

# Autonomous Drone Racing: A Survey

> Autonomous Drone Racing: A Survey | IEEE Transactions on Robotics 2024 | Drew Hanover, Antonio Loquercio, Leonard Bauersfeld, Angel Romero, Robert Penicka, Yunlong Song, Giovanni Cioffi, Elia Kaufmann, and Davide Scaramuzza

## Summary

This paper surveys autonomous drone racing as a benchmark for agile autonomy. The central idea is that racing forces onboard systems to solve perception, state estimation, planning, and control under unusually harsh timing, sensing, and aerodynamic constraints.

The survey also argues that ADR is more than a sport benchmark. It is a proxy for practical high-speed aerial applications where drones must navigate complex environments with limited compute and imperfect perception.

## Method

The paper first reviews drone modeling, including rigid-body kinematics, aerodynamic effects, motor and battery models, and sensor modeling for cameras and IMUs.

It then surveys the standard robotics stack for ADR:

- perception and state estimation,
- planning,
- control,
- and the hardware and simulation tools that support fast development.

A second major split is between model-based and learning-based approaches. The survey discusses how recent progress increasingly combines the two, especially as learning-based policies become more viable for direct high-speed control and sim-to-real transfer.

## Key Results

Because this is a survey, the main result is a field-level synthesis. The paper shows that ADR has advanced rapidly through benchmark competitions, better simulation tools, improved onboard estimation, more accurate aerodynamic modeling, and learning-based control.

One important framing from the paper is that lap time acts as a compact metric of progress across the full stack. To improve that one number, systems must solve many coupled problems at once.

The survey also identifies the remaining barriers to broadly useful ADR systems: robust perception under blur and lighting shifts, opponent-aware racing, generalization across tracks and tasks, safety, and the gap between closed racing tracks and real-world deployment scenarios.

## Hardware Used

- [[drones]]


## Related Work

For this vault, this survey is the historical spine for [[autonomous_drone_racing]], much as [[autonomous_vehicles_on_the_edge]] is for four-wheeled racing.

It pairs especially well with [[champion_level_drone_racing_using_deep_reinforcement_learning]], which can be read as one of the major milestones the survey points toward, and with [[safety_assured_high_speed_navigation_for_mavs]], which extends the discussion from fixed racing tracks toward safer unknown-environment navigation.

It also complements [[high_speed_perception]] and [[Highly_dynamic_autonomous_system]] by spelling out why cameras, IMUs, aerodynamics, battery models, and onboard compute all matter simultaneously in agile flight.

## Notes / Critique

The best part of the paper is that it treats drone racing as an end-to-end systems problem instead of only an RL or control problem. That makes it a much better bridge between racing, robotics, and deployment questions.

The main limitation is timing. It is already slightly pre-Swift-as-history and definitely pre-SUPER, so newer work should be read as updating parts of the survey’s challenge map rather than replacing the survey itself.
