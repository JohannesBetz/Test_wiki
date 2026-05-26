---
tags: [paper]
date: 2026-05-13
task: robotics
venue: "IEEE Robotics and Automation Letters 2024"
sources: 1
year: "2024"
doi: "10.1109/LRA.2024.3371288"
topic:
  - autonomous_drone_racing
  - high_speed_perception
  - Highly_dynamic_autonomous_system
tech_backbone: []
tech_representation: []
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: [race_against_the_machine_dataset]
models_used: []
hardware_used: [drones]
simulators_used: []
---

# Race Against the Machine: A Fully-Annotated, Open-Design Dataset of Autonomous and Piloted High-Speed Flight

> Race Against the Machine: A Fully-Annotated, Open-Design Dataset of Autonomous and Piloted High-Speed Flight | IEEE Robotics and Automation Letters 2024 | Michael Bosello, Davide Aguiari, Yvo Keuter, Enrico Pallotta, Sara Kiade, Gyordan Caminati, Flavio Pinzarrone, Junaid Halepota, Jacopo Panerati, and Giovanni Pau

## Summary

This paper introduces a fully annotated open dataset for aggressive high-speed flight, including both autonomous and human-piloted trajectories.

Its main value for this vault is not a controller, but a public measurement substrate for studying fast aerial autonomy under conditions that are usually underrepresented in open robotics datasets.

## Method

The paper presents an open-design dataset focused on high-speed flight.

That matters because many high-speed autonomy problems depend on data quality as much as on model design. Perception, state estimation, imitation, benchmarking, and autonomy-versus-human comparison all become easier to study when synchronized aggressive-flight data are publicly available and richly annotated.

The autonomous-and-piloted pairing is especially useful. It means the dataset can support both purely autonomous learning pipelines and analyses of how machine and human behavior differ in high-speed flight.

## Key Results

For this vault, the most important result is infrastructural: the paper strengthens the data layer of high-speed aerial autonomy.

That makes it a useful complement to performance papers such as [[champion_level_drone_racing_using_deep_reinforcement_learning]] and [[racevla_vla_based_racing_drone_navigation_with_human_like_behaviour]], which need high-quality data and benchmarking context even when their main contribution is algorithmic.

## Hardware Used

- [[drones]]


## Related Work

This paper belongs naturally near [[autonomous_drone_racing]] and [[high_speed_perception]], because public high-speed flight datasets are exactly the kind of resource those branches need.

It also pairs well with [[swift_drone_racing_data]], but the emphasis is different. Swift's released data support a particular champion-level racing result, while this paper is explicitly a dataset paper designed as an open resource in its own right.

Compared with [[autonomous_drone_racing_a_survey]], this paper is not a field overview but a concrete answer to one of the survey's recurring bottlenecks: the scarcity of open, realistic high-speed aerial datasets.

## Notes / Critique

The strongest contribution is that it turns a hard-to-study regime into a more measurable one. In highly dynamic autonomy, open data are often the missing middle layer between isolated demos and reproducible science.

For the vault, this paper is valuable because it gives the drone-racing and high-speed-perception branches a more explicit public-data anchor.
