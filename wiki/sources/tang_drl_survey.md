---
tags: [source]
date: 2026-05-08
sources: 1
---

# Tang DRL Survey Source

> Source: `raw/pdfs/Tang_DRL_Survey.pdf`
> Paper: Deep Reinforcement Learning for Robotics: A Survey of Real-World Successes, Annual Review of Control, Robotics, and Autonomous Systems 2025

## Summary

This paper surveys deep reinforcement learning in robotics with one clear filter: it focuses on cases that achieved at least some degree of real-world success rather than only simulation performance.

For this vault, the paper is useful because it places autonomous racing inside a wider landscape of robotic competencies where DRL has or has not matured in practice.

## Method

The survey organizes the literature along four axes:

- robot competencies learned with DRL,
- problem formulation,
- solution approach,
- and level of real-world success.

It distinguishes single-robot competencies such as locomotion, navigation, and manipulation from multi-agent competencies such as human-robot and multirobot interaction. The paper then compares how DRL is used across those domains and how much real-world deployment evidence exists in each.

## Evaluation

Because this is a survey, the main output is not a benchmark score but a characterization of maturity. The paper highlights champion-level drone racing and advanced quadruped locomotion as strong real-world DRL success stories, while noting that areas such as urban autonomous driving remain much less mature.

The main emphasis is on what made the successful cases work: sample efficiency improvements, structured priors, sim-to-real pipelines, careful evaluation, and tight coupling between learning and the robot's physical constraints.

## Notes / Critique

The strongest contribution is the realism filter. Many DRL surveys treat simulation results and physical deployment too similarly; this one tries to separate them explicitly.

Its main limitation for this vault is breadth. The paper is not about racing specifically, so its value here is mainly as adjacent context for reinforcement learning, embodied autonomy, and highly dynamic robotic systems.

## Pages Created From This Source

- [[deep_reinforcement_learning_for_robotics_a_survey_of_real_world_successes]]
- [[real_world_robotic_reinforcement_learning]]
