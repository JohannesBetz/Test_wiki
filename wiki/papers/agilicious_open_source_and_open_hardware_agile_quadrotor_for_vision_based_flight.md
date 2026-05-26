---
tags: [paper]
date: 2026-05-26
task: Highly_dynamic_autonomous_system
venue: "Science Robotics 2022"
sources: 1
year: "2022"
topic:
  - autonomous_drone_racing
  - agile_robotics
tech_backbone: []
tech_representation: []
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
hardware_used: [drones]
simulators_used: []
doi: "10.1126/scirobotics.abl9747"
---

# Agilicious: Open-Source and Open-Hardware Agile Quadrotor for Vision-Based Flight

> Agilicious: Open-Source and Open-Hardware Agile Quadrotor for Vision-Based Flight | Science Robotics 2022 | Philipp Foehn, Elia Kaufmann, Angel Romero, Robert Penicka, Sihao Sun, Leonard Bauersfeld, Thomas Laengle, Giovanni Cioffi, Yunlong Song, Antonio Loquercio, and Davide Scaramuzza | DOI: 10.1126/scirobotics.abl9747

## Summary

This paper introduces **Agilicious**, a co-designed open-source and open-hardware quadrotor system tailored for autonomous, agile vision-based flight. It bridges the gap in the drone research community for a standardized, high-performance physical platform that supports both model-based controllers and neural-network policies in real-world environments.

## Method

Agilicious features a highly integrated hardware and software stack:
- **Agile Hardware**: High thrust-to-weight and torque-to-inertia ratios, onboard vision sensors, and Nvidia Jetson GPU-accelerated compute hardware for real-time perception and neural network inference.
- **Software Stack**: A modular, real-time flight controller supporting various command representations (such as body rates, collective thrust, and single-rotor thrusts).
- **Control Modalities**: Native support for both model-based controllers (such as MPC) and neural-network-based policies trained via reinforcement learning.
- **Simulation**: Seamless integration with virtual-reality environments for hardware-in-the-loop (HIL) simulation.

## Key Results

Agilicious has been successfully demonstrated in both motion-capture arenas and open unstructured environments:
- Trajectory tracking at up to **5 g acceleration** and **70 km/h speed** inside motion capture systems.
- Closed-loop vision-based acrobatic flight and obstacle avoidance in the wild using purely onboard perception.
- Established a unified, reproducible baseline for testing and comparing quadrotor controllers.

## Hardware Used

- [[drones]] (Agilicious platform)

## Funding / Grants

- Supported by the European Research Council (ERC) Consolidator Grant [[agileflight]].

## Related Work

This paper acts as the physical embodiment foundation for subsequent milestones in the vault:
- **Control Stack**: Served as the baseline platform for [[champion_level_drone_racing_using_deep_reinforcement_learning|Swift]].
- **Optimal Control comparison**: Provided the testing framework for *Reaching the Limit in Autonomous Racing: Optimal Control vs. Reinforcement Learning* (Science Robotics 2023).

## Notes / Critique

Agilicious addresses a crucial bottleneck in aerial robotics: the lack of accessible, high-performance hardware platforms. By releasing the design open-source and open-hardware, the Scaramuzza Lab lowered the barrier to entry for physical sim-to-real research.
