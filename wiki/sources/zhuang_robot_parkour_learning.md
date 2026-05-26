---
tags: [source]
date: 2026-05-22
sources: 1
---

# Zhuang Robot Parkour Learning Source

> Source: `raw/pdfs/Zhuang_Robot_Parkour.pdf`
> Paper: Robot Parkour Learning, CoRL 2023

## Summary

This paper studies how a low-cost quadrupedal robot can learn a single end-to-end vision-based parkour policy that covers a diverse set of obstacle-crossing skills in the real world.

For this vault, the paper matters because it is an early strong parkour-style agility result on quadrupeds and a direct precursor to the later humanoid parkour line.

## Method

From the public record and local metadata, the system uses:

- an end-to-end vision-based parkour policy,
- [[reinforcement_learning]] for learning diverse parkour skills,
- and a distillation step that compresses those skills into one deployment-ready policy using an egocentric depth camera.

The paper describes the RL procedure as being inspired by direct collocation, which gives it a slightly different flavor from more standard end-to-end locomotion training.

## Evaluation

According to the public abstract and project page, the learned system enables low-cost quadrupeds to autonomously select and execute climbing, leaping, crawling, squeezing, and running behaviors to traverse challenging real-world environments.

For this vault, the key result is diversity under one policy: the robot is not learning one gait or one stunt, but a small parkour repertoire.

## Notes / Critique

The strongest contribution is the combination of diversity and perception. The controller is both vision-based and skill-diverse, which makes it more interesting than either blind locomotion or highly specialized obstacle solvers.

That makes it a strong complement to:

- [[humanoid_parkour_learning]], which ports the parkour framing into the humanoid setting,
- [[learning_robust_perceptive_locomotion_for_quadrupedal_robots_in_the_wild]], which emphasizes robust perceptive locomotion,
- and [[perceptive_locomotion_through_nonlinear_model_predictive_control]], which gives the model-based perceptive-control alternative.

## Pages Created From This Source

- [[robot_parkour_learning]]
