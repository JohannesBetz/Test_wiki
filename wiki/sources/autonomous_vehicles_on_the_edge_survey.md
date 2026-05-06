---
tags: [source]
date: 2026-05-06
sources: 1
---

# Autonomous Vehicles on the Edge Survey

> Source: `Racing-Survey/Autonomous_Racing_Survey_Main_File.pdf`

## Summary

This survey by Betz, Zheng, Liniger, Rosolia, Karle, Behl, Krovi, and Mangharam is the foundational overview of [[autonomous_vehicle_racing|autonomous vehicle racing]] through the end of 2021. It frames autonomous racing as autonomous driving at the handling limits: high speed, high acceleration, short reaction times, uncertain sensing, and eventually adversarial multi-agent interaction.

The paper organizes the field around the classical autonomy pipeline of [[high_speed_perception|perception]], [[autonomous_racing_planning|planning]], and [[autonomous_racing_control|control]], then adds [[end_to_end_autonomous_racing|end-to-end learning]], applied studies, simulation, vehicle modeling, and [[autonomous_racing_platforms|hardware/competition platforms]]. Its bibliography is indexed separately in [[autonomous_racing_survey_bibliography]]. Its main value for this wiki is not just as a paper list, but as an early taxonomy for how autonomous racing research was grouped before the field expanded into newer highly dynamic autonomy domains.

## Scope

The survey intentionally focuses on four-wheeled autonomous racecars, not drone racing or high-speed highway autonomy. It includes small-scale cars, Formula Student Driverless vehicles, Roborace, and the Indy Autonomous Challenge, as long as the research has a clear racing setting, racing platform, racing simulator, or racing-specific problem.

## Main Taxonomy

- [[high_speed_perception|Perception]]: mapping, localization, free-space detection, cone/object detection, and state estimation at high speeds.
- [[autonomous_racing_planning|Planning]]: global raceline generation, local motion planning, behavioral planning, overtaking, and interaction-aware planning.
- [[autonomous_racing_control|Control]]: reference tracking at the handling limits, MPC variants, learning-based control, and drifting.
- [[end_to_end_autonomous_racing|End-to-end approaches]]: optimization, deep learning, reinforcement learning, partial end-to-end pipelines, and full end-to-end driving policies.
- [[autonomous_racing_platforms|Platforms]]: F1TENTH, Formula Student Driverless, AutoRally, Roborace, Indy Autonomous Challenge, EV Grand Prix Autonomous, and other small-scale racecars.
- [[autonomous_racing_simulation|Simulation]]: TORCS, Learn-to-Race / Roborace Simulator, SVL Simulator, F1TENTH Gym, F1TENTH Simulator, and CARLA-based racing CI/testing.

## Key Findings

The survey shows a strong skew toward planning and control, with comparatively less racing-specific perception research. Most perception papers adapt existing SLAM, localization, object detection, or sensor-fusion methods rather than designing algorithms specifically for high-speed racing. A recurring gap is reliable long-range object detection and localization under motion blur, synchronization error, sparse landmarks, and high closing speeds.

Planning research divides into global planning, local planning, and behavioral planning. Global planning optimizes a raceline using minimum time, minimum curvature, energy-aware objectives, evolutionary algorithms, or optimal control. Local planning handles dynamic feasibility and obstacle avoidance, often with MPC, graph search, splines, RRT variants, or sampled motion primitives. Behavioral planning is still comparatively young and relies heavily on cost-weighted candidate selection or game-theoretic approaches.

Control research is the deepest portion of the field. The survey emphasizes that autonomous racing control must track path, heading, and velocity accurately while the vehicle is close to tire and stability limits. MPC, especially NMPC, MPPI, tube MPC, stochastic MPC, and learning MPC, appears as the dominant family. Learning-based control is valuable because repeated laps provide data that can improve tracking, compensate modeling errors, or identify vehicle parameters.

End-to-end racing is presented as promising but fragile. The racing domain simplifies some perception and decision problems, but high-speed failures, data diversity, simulation-to-reality transfer, vehicle/tire dynamics, and out-of-distribution events remain core barriers. The survey notes that partial end-to-end approaches, where neural networks output intermediate representations such as waypoints or trajectories, can outperform direct pixel-to-control designs.

## Open Challenges

The survey names nine open research challenges:

1. Autonomous high-speed perception.
2. Multi-vehicle trajectory planning.
3. Multi-vehicle interaction.
4. Adversarial driving.
5. Real-time vehicle dynamics modeling.
6. Balancing safety and performance.
7. Autonomous racing regulations and rulebook.
8. Overall software application and real-time stack performance.
9. Autonomous high-speed hardware.

These challenges make the source useful as a baseline for comparing later work in [[Highly_dynamic_autonomous_system|highly dynamic autonomous systems]], especially where newer papers address agility, interaction, sim-to-real transfer, or safety-performance tradeoffs.

## Notes / Critique

The paper is broad and systematic, but its cut-off means it should be treated as a baseline rather than a current state-of-the-art map. It predates many later developments in large foundation models, generative simulation, world models, VLM/MLLM-based scenario understanding, and newer robotics work on agile drones, humanoids, and quadrupeds. Future wiki updates should use this survey as the historical spine, then explicitly mark which claims are superseded by post-2021 work.

The PDF text extraction contains some OCR/layout artifacts, especially in tables. Table-derived entries should be checked against the original PDF before creating detailed individual paper pages.

## Pages Created From This Source

- [[autonomous_vehicles_on_the_edge]]
- [[autonomous_racing_survey_bibliography]]
- [[autonomous_vehicle_racing]]
- [[Highly_dynamic_autonomous_system]]
- [[high_speed_perception]]
- [[autonomous_racing_planning]]
- [[autonomous_racing_control]]
- [[end_to_end_autonomous_racing]]
- [[autonomous_racing_platforms]]
- [[autonomous_racing_simulation]]
- [[model_predictive_control]]
- [[reinforcement_learning]]
- [[f1tenth]]
- [[roborace]]
- [[formula_student_driverless]]
- [[indy_autonomous_challenge]]
- [[torcs]]
- [[svl_simulator]]
- [[f1tenth_gym]]
- [[carla]]
