---
tags: [paper]
date: 2026-05-07
task: Highly_dynamic_autonomous_system
venue: "Nature 2026"
sources: 1
topic:
  - robot_table_tennis
  - high_speed_perception
  - human_robot_interaction
  - reinforcement_learning
  - sim_to_real_transfer
tech_backbone: [cnn]
tech_representation: []
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: [ace]
simulators_used: [table_tennis_simulation]
doi: "10.1038/s41586-026-10338-5"
---

# Outplaying Elite Table Tennis Players With an Autonomous Robot (2026)

> Outplaying elite table tennis players with an autonomous robot | Nature 2026 | Dürr et al.

## Summary

This paper presents [[ace]], an autonomous table-tennis robot that plays competitive real-world matches against elite and professional players under official competition rules. It is a major example of [[Highly_dynamic_autonomous_system|highly dynamic autonomy]] because the system must perceive, decide, and act within human reaction-time limits while handling high-speed, high-spin adversarial shots near obstacles.

## Method

Ace integrates perception, control, and custom robot hardware:

- Nine APS cameras localize the ball in 3D at 200 Hz with reported average 3.0 mm error and 10.2 ms latency.
- Three gaze-control systems combine [[event_based_vision]] cameras, pan/tilt mirrors, and tunable telephoto lenses to track the ball and estimate spin.
- Ball spin is estimated asynchronously using a low-latency CNN estimator and a higher-accuracy contrast-maximization estimator.
- Rally control uses model-free [[reinforcement_learning]], specifically [[soft_actor_critic]], trained entirely in simulation on single-shot returns.
- The learning setup is an [[asymmetric_actor_critic]]: the critic sees simulator ground-truth ball state, while the policy sees histories of noisy sensor measurements to support real-world transfer.
- Policy actions live in an abstract space and are mapped to feasible joint positions/velocities, which become terminal constraints for a convex trajectory optimization problem.
- A near-time-optimal MPC reset planner computes safe reset trajectories so the robot can return to a dexterous configuration for the next shot.
- Serves are produced from a library: human-demonstrated tosses are retargeted to the robot, strike trajectories are optimized in simulation with a genetic algorithm, and candidate serves are evaluated on the real robot by expert players.

## Key Results

Ace was evaluated in April 2025 against five elite players and two professional players who faced the robot for the first time. It won three of five matches against elite players, with seven games won out of 13. It lost both matches against professional players, winning one game out of seven.

Technically, Ace returned shots up to 14 m/s consistently and maintained more than 75% return rate up to 450 rad/s spin. The maximum opponent shot returned by Ace had 19.6 m/s linear velocity and 867 rad/s angular velocity. Ace itself produced maximum ball velocities of 16.4 m/s and 600 rad/s.

Ace won points more through consistent returns and spin diversity than through overwhelming speed. Its serve library generated 16 direct serve points against elite players and four against professional players.

## Datasets Used

The paper reports that all data needed to evaluate the conclusions are present in the paper or supplementary materials. It does not introduce a named static dataset page for the wiki.

## Related Work

The paper explicitly follows [[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]] and [[champion_level_drone_racing_using_deep_reinforcement_learning]] as examples of deep RL reaching champion-level performance in racing tasks. Compared with [[gt_sophy]], Ace is a physical robot rather than a simulator agent. Compared with [[swift]], Ace includes direct physical interaction with human opponents who influence the task dynamics every shot.

The perception stack connects to [[event_based_vision_a_survey]] and to the broader [[high_speed_perception]] problem: low latency, high spin, high speed, and motion blur make standard frame-based sensing insufficient by itself.

## Notes / Critique

Ace is best read as a full-stack system result rather than a single algorithm result. The performance depends on high-speed sensing, spin estimation, simulation, RL policy training, trajectory optimization, safe reset behavior, serve engineering, and custom hardware.

The main open problem is opponent modeling and online adaptation. The authors note that zero-shot sim-to-real transfer is hard because human behavior is difficult to model; without that model, the true win/loss objective is unavailable during training and must be replaced by surrogate shot-return objectives.
