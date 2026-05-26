---
tags: [source]
date: 2026-05-22
sources: 1
---

# Margolis Rapid Locomotion Quadruped Source

> Source: `raw/pdfs/Margolis_Rapid-locomotion_Quadruped.pdf`
> Paper: Rapid Locomotion via Reinforcement Learning, arXiv 2022

## Summary

This paper studies how a quadrupedal robot can achieve very fast locomotion in the real world using a controller learned through reinforcement learning.

For this vault, the paper matters because it is one of the clearest examples that high-speed embodied competence in legged robotics can emerge from structured experience rather than only from hand-engineered gait design.

## Method

The paper proposes an end-to-end learned locomotion controller for the MIT Mini Cheetah trained in simulation and transferred to the real robot.

The two main ingredients, based on the recoverable public arXiv record and the local PDF traces, are:

- an adaptive curriculum over velocity commands,
- and an online system-identification strategy for sim-to-real transfer.

That makes the paper especially relevant to this vault's broader themes of [[reinforcement_learning]], [[curriculum_learning]], and [[sim_to_real_transfer]].

## Evaluation

The paper's headline claim is that the robot achieves unusually agile and rapid locomotion in the wild, including sustained high speeds and robust turning on natural terrain such as grass, gravel, and ice.

For this vault, the key point is not only the speed number, but the fact that the result helps establish quadruped locomotion as one of the stronger real-world success cases for aggressive learned embodied control.

## Notes / Critique

The strongest contribution is not only raw performance. It is the combination of:

- fast physical behavior,
- model-free learning,
- adaptive curriculum structure,
- and a practical sim-to-real bridge.

That combination makes the paper a strong complement to the newer [[high_speed_control_and_navigation_for_quadrupedal_robots_on_complex_and_discrete_terrain]] paper: one emphasizes rapid learned locomotion in the wild, while the other emphasizes tight coupling between control and navigation on complex discrete terrain.

## Pages Created From This Source

- [[rapid_locomotion_via_reinforcement_learning]]
