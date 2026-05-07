---
tags: [source]
date: 2026-05-07
sources: 1
---

# Champion-Level Drone Racing Source

> Source: `raw/pdfs/Scaramuzza_Champion-level_drone_racing.pdf`

## Summary

This Nature paper introduces [[swift|Swift]], an autonomous FPV drone-racing system that reaches champion-level performance using only onboard sensing and onboard computation. The system combines a visual-inertial perception stack with a learned control policy trained by [[proximal_policy_optimization]] in simulation and fine-tuned through [[empirical_residual_modeling|empirical residual models]] fitted from short real-world rollouts.

The paper is important for this wiki because it extends the [[autonomous_vehicle_racing]] baseline into [[autonomous_drone_racing]] and [[Highly_dynamic_autonomous_system|highly dynamic autonomous systems]]. Unlike many earlier drone-racing systems, Swift does not rely on external motion capture at deployment time. It raced physical quadrotors against three human FPV champions and achieved the fastest recorded race time in the event.

## System

Swift has two main modules:

- Perception: [[visual_inertial_odometry]] from an Intel RealSense T265, a U-Net gate detector, camera resectioning/IPPE for relative gate pose, and a Kalman filter that fuses gate-based pose corrections with VIO.
- Control: a two-layer MLP policy trained with model-free on-policy deep [[reinforcement_learning]] using PPO. The policy outputs mass-normalized collective thrust and body-rate commands.

The policy reward combines progress toward the next gate, a perception objective that keeps the next gate in the camera field of view, action smoothness, and crash penalties. This makes the controller perception-aware rather than only time-optimal.

## Key Results

- Swift raced against Alex Vanover, Thomas Bitmatta, and Marvin Schaepper on a physical 75 m track with seven gates.
- It won 15 of 25 head-to-head races overall.
- It recorded the fastest three-lap race time, 17.465 s, and the fastest single-lap median among competitors in the reported time-trial data.
- Swift was especially strong at the start and in tight turns such as the split-S, where it found tighter maneuvers than human pilots.
- Losses were attributed to collisions with the opponent, collisions with gates, or being slower than the human pilot.

## Method Details

The central sim-to-real idea is not broad domain randomization, but small-data residual modeling. The authors collect about three real-world rollouts, roughly 50 s of flight, compare onboard estimates and dynamics against motion-capture ground truth during training runs, and fit:

- Gaussian-process residual observation models for VIO/perception drift.
- k-nearest-neighbour residual dynamics models for unmodelled accelerations.

These residual models are injected into simulation, and the control policy is fine-tuned there. Controlled simulations show that zero-shot RL, domain randomization, and time-optimal MPC baselines degrade sharply under observation/dynamics shifts, while Swift remains able to complete laps.

## Notes / Critique

Swift demonstrates a strong hybrid recipe for high-speed autonomy: learned control, engineered perception, explicit state estimation, and empirical real-world residual modeling. This is directly relevant to safety-performance tradeoffs in autonomous racing and agile robotics.

The limitations are also important. Swift is not opponent-aware, so it always pushes for fastest expected completion rather than adapting race strategy. It is not trained to recover after crashes. Its perception assumes similar appearance conditions to training, making illumination and environment shifts a likely failure mode unless the detector and residual observation model are diversified.

## Pages Created From This Source

- [[champion_level_drone_racing_using_deep_reinforcement_learning]]
- [[swift]]
- [[autonomous_drone_racing]]
- [[sim_to_real_transfer]]
- [[visual_inertial_odometry]]
- [[proximal_policy_optimization]]
- [[empirical_residual_modeling]]
- [[swift_drone_racing_data]]
