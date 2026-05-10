---
tags: [paper]
date: 2026-05-07
task: Highly_dynamic_autonomous_system
venue: "Nature 2023"
sources: 1
year: "2023"
topic:
  - autonomous_drone_racing
  - high_speed_perception
  - end_to_end_learning
  - sim_to_real_transfer
  - agile_robotics
tech_backbone: [cnn]
tech_representation: []
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: [swift_drone_racing_data]
models_used: [swift]
simulators_used: [quadrotor_simulation]
doi: "10.1038/s41586-023-06419-4"
---

# Champion-Level Drone Racing Using Deep Reinforcement Learning (2023)

> Champion-level drone racing using deep reinforcement learning | Nature 2023 | Kaufmann et al.

## Summary

This paper presents [[swift]], an autonomous FPV drone-racing system that reaches world-champion-level performance in physical head-to-head drone races using only onboard sensors and computation. The result is a milestone for [[Highly_dynamic_autonomous_system|highly dynamic autonomous systems]] because Swift competes under real sensing, latency, dynamics, and actuation constraints rather than relying on external motion capture at deployment.

## Method

Swift combines a traditional perception/state-estimation stack with a learned racing policy:

- A [[visual_inertial_odometry]] module estimates motion from camera and IMU.
- A U-Net-style gate detector identifies racing-gate corners in onboard images.
- Gate detections are converted into relative pose estimates and fused with VIO using a Kalman filter.
- A two-layer MLP control policy maps the fused state, next-gate geometry, and previous action to collective thrust and body-rate commands.
- The policy is trained with [[proximal_policy_optimization]] in simulation.
- [[sim_to_real_transfer]] is handled by [[empirical_residual_modeling]]: Gaussian-process observation residuals and k-nearest-neighbour dynamics residuals are fitted from short real-world flight rollouts and injected into simulation for policy fine-tuning.

The reward combines progress toward the next gate, perception awareness, smoothness, and crash penalties. The perception-aware term encourages the drone to keep the next gate visible, improving state estimation during aggressive flight.

## Key Results

Swift competed against Alex Vanover, Thomas Bitmatta, and Marvin Schaepper on a 75 m, seven-gate physical track. It won 15 of 25 head-to-head races and achieved the fastest recorded three-lap race time at 17.465 s. Against individual pilots, it won 5 of 9 races against Vanover, 4 of 7 against Bitmatta, and 6 of 9 against Schaepper.

Segment analysis shows Swift gaining time at the start and in tight turns, especially the split-S. The authors attribute this partly to lower sensorimotor latency and to the RL policy finding tight maneuvers that optimize longer-horizon progress. Human pilots remained stronger in robustness and strategy adaptation, especially after crashes or when choosing risk levels during a race.

## Datasets Used

- [[swift_drone_racing_data]]: motion-capture recordings and analysis code released on Zenodo.

## Related Work

The paper connects to [[autonomous_vehicles_on_the_edge]] by addressing several open challenges from autonomous racing in a drone domain: high-speed perception, real-time dynamics modeling, sim-to-real transfer, and balancing safety against performance. It also complements racing RL work such as [[super_human_performance_in_gran_turismo_sport_using_deep_reinforcement_learning]] and [[autonomous_overtaking_in_gran_turismo_sport_using_curriculum_reinforcement_learning]], but moves the claim from simulation/game settings to real physical racing.

## Notes / Critique

Swift is best read as a hybrid system rather than a pure end-to-end policy. The learned policy is powerful, but it depends on an engineered perception pipeline, known track/gate map, Kalman filtering, real-world residual fitting, and a low-level Betaflight controller.

The strongest limitation is robustness. Swift was not trained for crash recovery, is not opponent-aware, and assumes visual conditions close to those seen during training. This makes it less strategically flexible than human racers even though it can be faster over clean laps.
