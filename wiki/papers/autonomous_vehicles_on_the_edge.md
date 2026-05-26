---
tags: [paper]
date: 2026-05-06
task: autonomous_racing
venue: "IEEE OJ-ITS 2023"
sources: 1
year: "2023"
topic:
  - autonomous_racing_survey
  - high_speed_perception
  - planning
  - control
  - end_to_end_learning
  - simulation
  - hardware_platforms
tech_backbone: []
tech_representation: []
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
hardware_used: [cars_and_race_cars]
simulators_used: [carla, f1tenth_gym, roborace_simulator, svl_simulator, torcs]
---

# Autonomous Vehicles on the Edge (2023)

> Autonomous Vehicles on the Edge: A Survey on Autonomous Vehicle Racing | IEEE OJ-ITS 2023 | Betz et al.

## Summary

This survey is the main baseline paper for [[autonomous_vehicle_racing]]. It reviews 233 papers and organizes autonomous racing research around [[high_speed_perception]], [[autonomous_racing_planning]], [[autonomous_racing_control]], [[end_to_end_autonomous_racing]], applied studies, simulation, vehicle dynamics modeling, and [[autonomous_racing_platforms]].

The paper defines autonomous racing as four-wheeled vehicle autonomy in a racing setting, including small-scale cars, Formula Student Driverless, Roborace, Indy Autonomous Challenge, and racing simulators. It excludes high-speed highway driving when the work lacks operation at the handling limits or adversarial/racing context.

The survey's BibTeX library is indexed in [[autonomous_racing_survey_bibliography]], with lightweight stubs for each referenced work.

## Method

The survey uses the perception-planning-control autonomy pipeline as its main organizing structure. It then categorizes papers by research objective, method, whether the approach was tested on hardware, racing series/platform, and, where available, maximum speed.

For hardware, it compares small-scale platforms and full-size racing platforms by vehicle parameters, powertrain, sensors, compute, software, competition format, simulation support, and related papers.

## Key Results

- [[autonomous_racing_control|Control]] and [[autonomous_racing_planning|planning]] dominate the field, especially MPC and optimal-control-based methods.
- [[high_speed_perception|Perception]] is underdeveloped relative to planning/control; many approaches adapt standard SLAM, localization, sensor fusion, and object detection.
- [[model_predictive_control|Model predictive control]] appears across both planning and control, from local trajectory planning to path/velocity tracking at the handling limits.
- [[reinforcement_learning|Reinforcement learning]] and deep learning are active in [[end_to_end_autonomous_racing]], but generalization, sim-to-real transfer, high-speed failures, and data requirements remain major weaknesses.
- The main platforms covered are [[f1tenth]], [[formula_student_driverless]], [[roborace]], [[indy_autonomous_challenge]], EV Grand Prix Autonomous, AutoRally, and 1:43 ORCA cars.
- The main simulators covered are [[torcs]], [[svl_simulator]], [[f1tenth_gym]], F1TENTH Simulator, Learn-to-Race / Roborace Simulator, and [[carla]]-based testing.

## Datasets Used

The survey does not center a benchmark dataset. It highlights the lack of public datasets for high-speed autonomous racing perception and notes that this limits systematic progress on racing-specific sensing and detection.

## Hardware Used

- [[cars_and_race_cars]]


## Related Work

This page is the historical spine for later wiki pages on [[Highly_dynamic_autonomous_system|highly dynamic autonomous systems]]. It should be linked from later papers that address the survey's open challenges, especially high-speed perception, multi-agent planning, adversarial racing, real-time vehicle modeling, and safety-performance tradeoffs.

## Notes / Critique

The survey gives a strong pre-2022 map of autonomous racing, but it predates the wave of foundation-model and generative-world-model work. Treat its open challenges as a baseline: later work should either confirm, refine, or supersede them.
