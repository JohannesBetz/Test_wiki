---
tags: [source]
date: 2026-05-07
sources: 1
---

# Outplaying Table Tennis Source

> Source: `raw/pdfs/Wurman_Outplaying-TennisPlayer.pdf`

## Summary

This Nature paper introduces [[ace]], an autonomous table-tennis robot that plays competitive real-world matches against elite and professional human players under official table-tennis rules. The paper is important for [[Highly_dynamic_autonomous_system|highly dynamic autonomous systems]] because it moves beyond simulated racing and static real-world tasks into fast, adversarial, physical human-robot interaction.

Ace combines a high-speed perception system, model-free [[reinforcement_learning]], safe trajectory generation, and custom high-speed robot hardware. Its perception stack uses conventional APS cameras for 3D ball localization and [[event_based_vision]] sensors in gaze-control systems for ball spin estimation.

## System

Ace has three main components:

- Perception: nine APS cameras localize the ball in 3D at 200 Hz; three event-camera gaze-control systems estimate angular velocity at roughly 400-700 Hz.
- Control: rally policies are trained in simulation with [[soft_actor_critic]] using an [[asymmetric_actor_critic]] setup in which the critic receives ground-truth simulator state while the policy receives noisy sensor histories.
- Hardware: a custom eight-degree-of-freedom robot with synchronized actuators, low-latency position feedback, a racket end effector, and a serving cup.

During rallies, the learned policy is queried every 32 ms and outputs abstract actions that are mapped to feasible joint positions and velocities. Those become terminal constraints for an optimization problem that generates a 1 kHz trajectory segment. In parallel, a safe reset trajectory is generated so the robot can recover to a dexterous configuration for the next shot.

## Key Results

- Ace won three of five matches against elite players.
- It lost both matches against professional players, winning one of seven games.
- It returned shots up to 14 m/s consistently and showed a drop above 16 m/s, similar to human players.
- It returned a broad range of spins, with more than 75% return rate up to 450 rad/s.
- It returned opponent shots with maximum measured velocity 19.6 m/s and angular velocity 867 rad/s.
- Its serve library produced 16 direct points against elite players and four against professional players.
- It reacted to rare net-contact shots within about 49 ms, illustrating fast perception-control adaptation.

## Notes / Critique

The strongest contribution is the integration of perception, learning, and hardware under realistic match rules. The paper deliberately avoids simplifying constraints that earlier robot table-tennis systems often used, such as ball launchers, modified rackets, restricted court regions, or omitting serves.

The main limitation is high-level tactics and adaptation. The authors note that zero-shot transfer from simulation to reality is hard because human behavior is difficult to model in a high-dimensional physical space. Without a good human opponent model, the true objective of winning is not directly available during training, so Ace relies on surrogate objectives.

## Pages Created From This Source

- [[outplaying_elite_table_tennis_players_with_an_autonomous_robot]]
- [[ace]]
- [[robot_table_tennis]]
- [[event_based_vision]]
- [[soft_actor_critic]]
- [[asymmetric_actor_critic]]
