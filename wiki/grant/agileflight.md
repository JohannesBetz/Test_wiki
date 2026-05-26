---
tags: [source]
date: 2026-05-26
sources: 2
grant_id: "864042"
acronym: "AGILEFLIGHT"
coordinator: "Davide Scaramuzza"
host_institution: "Universitat Zurich"
start_date: "2020-09-01"
end_date: "2025-08-31"
funding_scheme: "ERC-COG - Consolidator Grant"
total_budget: "2,000,000.00 EUR"
---

# AGILEFLIGHT

## Project Metadata

| Key | Value |
| --- | --- |
| **Title** | Low-latency Perception and Action for Agile Vision-based Flight |
| **Acronym** | AGILEFLIGHT |
| **Grant ID** | 864042 |
| **Coordinator** | Davide Scaramuzza |
| **Host Institution** | Universitat Zurich (Switzerland) |
| **Funding Scheme** | ERC-COG - Consolidator Grant |
| **Funding Programme** | H2020-EU.1.1. - EXCELLENT SCIENCE - European Research Council (ERC) |
| **Total Cost / EU Contribution** | € 2,000,000.00 |
| **Start Date** | 2020-09-01 |
| **End Date** | 2025-08-31 |
| **Status** | Project Closed |
| **CORDIS Permalink** | [cordis.europa.eu/project/id/864042](https://cordis.europa.eu/project/id/864042) |

## Objective

Drones are disrupting industries like agriculture, delivery, and search-and-rescue, but they are either human-piloted or heavily reliant on GPS. Cameras provide an alternative, mapping environments locally to plan safe trajectories. However, autonomous drones still fall short of human pilots. While perception and control algorithms are mature, they lack robustness when handling unreliable state estimation, low-latency requirements, and real-time planning under severe resource constraints.

AGILEFLIGHT aims to develop novel scientific methods to demonstrate autonomous, vision-based, agile quadrotor navigation in unknown, GPS-denied, cluttered, and dynamic environments. The project will:
1. Develop robust, low-latency, multimodal perception algorithms that combine standard and event cameras.
2. Unify perception and state estimation with planning and control to execute agile maneuvers comparable to professional drone pilots.

## Relevance to the Vault

This grant is the major funding source behind the Scaramuzza Lab's key agile flight breakthroughs represented in this vault:
- **Agile Control System**: Funded the development of [[swift]], the champion-level vision-based FPV drone racing system described in [[champion_level_drone_racing_using_deep_reinforcement_learning]].
- **Perception Latency & Sensing**: Funded research on the physical and mathematical limits of perception-action latency in [[how_fast_is_too_fast_the_role_of_perception_latency_in_high]].
- **Event-Based Vision**: Directly supported the exploration of [[event_based_vision]] as a solution to high-speed dynamic tracking and low-latency navigation.
- **Topic Connection**: Deeply linked to [[autonomous_drone_racing]] and [[Highly_dynamic_autonomous_system]].

## Key Project Publications

For a full index, see the [[agileflight_publications]] source. Key outputs from the project are grouped below:

### 1. Agile Control & Reinforcement Learning (Vision & State Based)
- [[dream_to_fly_model_based_reinforcement_learning_for_vision_based_drone_flight|Dream to Fly: Model-Based Reinforcement Learning for Vision-Based Drone Flight]] (Angel Romero et al., ICRA 2026)
- [[learning_agile_quadrotor_flight_in_the_real_world|Learning Agile Quadrotor Flight in the Real World]] (Yunfan Ren et al., Arxiv 2026)
- Learning Quadrotor Control From Visual Features Using Differentiable Simulation (Johannes Heeg et al., ICRA 2025)
- Learning on the Fly: Rapid Policy Adaptation via Differentiable Simulation (J. Pan et al., RA-L 2026)
- [[actor_critic_model_predictive_control_differentiable_optimization_meets_reinforcement_learning_for_agile_flight|Actor-Critic Model Predictive Control: Differentiable Optimization meets Reinforcement Learning for Agile Flight]] (Angel Romero et al., T-RO 2025)
- Learning Acrobatic Flight from Preferences (Colin Merk et al., Arxiv 2026)
- Environment as Policy: Learning to Race in Unseen Tracks (Hongze Wang et al., ICRA 2025)
- Student-Informed Teacher Training (Nico Messikommer et al., ICLR 2025)
- Multi-task Reinforcement Learning for Quadrotors (Jiaxu Xing et al., RA-L 2025)
- Bootstrapping Reinforcement Learning with Imitation for Vision-Based Agile Flight (Jiaxu Xing et al., CoRL 2024)
- Demonstrating Agile Flight from Pixels without State Estimation (Ismail Geles et al., RSS 2024)
- Learning Agile, Vision-Based Drone Flight: From Simulation to Reality (Davide Scaramuzza & Elia Kaufmann, Robotics Research 2023)
- Reaching the Limit in Autonomous Racing: Optimal Control vs. Reinforcement Learning (Yunlong Song et al., Science Robotics 2023)
- [[champion_level_drone_racing_using_deep_reinforcement_learning|Champion-level Drone Racing using Deep Reinforcement Learning]] (Elia Kaufmann et al., Nature 2023)
- Learning Deep Sensorimotor Policies for Vision-based Autonomous Drone Racing (Jiawei Fu et al., IROS 2023)
- Learning Perception-Aware Agile Flight in Cluttered Environments (Yunlong Song et al., ICRA 2023)
- A Benchmark Comparison of Learned Control Policies for Agile Quadrotor Flight (Elia Kaufmann et al., ICRA 2022)
- Autonomous Drone Racing with Deep Reinforcement Learning (Y. Song et al., IROS 2021)
- Deep Drone Acrobatics (Elia Kaufmann et al., RSS 2020)

### 2. Low-Latency Event-Based Flight & Perception
- Approximate Imitation Learning for Event-based Quadrotor Flight in Cluttered Environments (Nico Messikommer et al., Arxiv 2026)
- Event-Aided Sharp Radiance Field Reconstruction for Fast-Flying Drones (Rong Zou et al., T-RO 2026)
- Low-Latency Event-Based Velocimetry for Quadrotor Control in a Narrow Pipe (Leonard Bauersfeld & Davide Scaramuzza, T-RO 2026)
- Monocular Event-Based Vision for Obstacle Avoidance with a Quadrotor (Anish Bhattacharya et al., CoRL 2024)
- Towards Low-Latency High-Bandwidth Control of Quadrotors using Event Cameras (R. Sugimoto et al., ICRA 2020)
- Dynamic Obstacle Avoidance for Quadrotors with Event Cameras (Davide Falanga et al., Science Robotics 2020)
- [[how_fast_is_too_fast_the_role_of_perception_latency_in_high|How Fast is Too Fast? The Role of Perception Latency in High-Speed Sense and Avoid]] (Davide Falanga et al., RA-L 2019)

### 3. Model Predictive Control & Trajectory Optimization
- Perception-Aware Time-Optimal Planning for Quadrotor Waypoint Flight (Chao Qin et al., Arxiv 2026)
- Unifying Quadrotor Motion Planning and Control by Chaining Different Fidelity Models (Rudolf Reiter et al., Arxiv 2025)
- MPCC++: Model Predictive Contouring Control for Time-Optimal Flight with Safety Constraints (Maria Krinner et al., RSS 2024)
- [[real_time_neural_mpc_deep_learning_model_predictive_control_for_quadrotors_and_agile_robotic_platforms|Real-time Neural MPC: Deep Learning Model Predictive Control for Quadrotors and Agile Robotic Platforms]] (Tim Salzmann et al., RA-L 2023)
- Weighted Maximum Likelihood for Controller Tuning (Angel Romero et al., ICRA 2023)
- Time-optimal Online Replanning for Agile Quadrotor Flight (Angel Romero et al., RA-L 2022)
- A Comparative Study of Nonlinear MPC and Differential-Flatness-Based Control for Quadrotor Agile Flight (Sihao Sun et al., T-RO 2022)
- Model Predictive Contouring Control for Time-Optimal Quadrotor Flight (A. Romero et al., T-RO 2022)
- Performance, Precision, and Payloads: Adaptive Nonlinear MPC for Quadrotors (Drew Hanover et al., RA-L 2021)
- Time-Optimal Planning for Quadrotor Waypoint Flight (Philipp Foehn et al., Science Robotics 2021)
- PAMPC: Perception-Aware Model Predictive Control for Quadrotors (Davide Falanga et al., IROS 2018)

### 4. State Estimation, Aerodynamics, & Platforms
- HDVIO2.0: Wind and Disturbance Estimation with Hybrid Dynamics VIO (Giovanni Cioffi & Leonard Bauersfeld, T-RO 2025)
- HDVIO: Improving Localization and Disturbance Estimation with Hybrid Dynamics VIO (Giovanni Cioffi & Leonard Bauersfeld, RSS 2023)
- Learned Inertial Odometry for Autonomous Drone Racing (Giovanni Cioffi et al., RA-L 2023)
- Robotics meets Fluid Dynamics: A Characterization of the Induced Airflow around a Quadrotor (Leonard Bauersfeld et al., RA-L 2024)
- [[agilicious_open_source_and_open_hardware_agile_quadrotor_for_vision_based_flight|Agilicious: Open-Source and Open-Hardware Agile Quadrotor for Vision-Based Flight]] (Philipp Foehn et al., Science Robotics 2022)
- NeuroBEM: Hybrid Aerodynamic Quadrotor Model (Leonard Bauersfeld et al., RSS 2021)
- The UZH-FPV Drone Racing Dataset (Jeffrey Delmerico et al., ICRA 2019)
- Flightmare: A Flexible Quadrotor Simulator (Yunlong Song et al., CoRL 2020)
- AlphaPilot: Autonomous Drone Racing (Philipp Foehn et al., RSS 2020)
