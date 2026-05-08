---
tags: [source]
date: 2026-05-08
sources: 1
---

# Bajcsy Vision-Based Pursuit-Evasion Source

> Source: `raw/pdfs/Bacjsi_Learning_Vision-based_Pursuit-Evasion_Robot_Policies.pdf`
> Paper: Learning Vision-based Pursuit-Evasion Robot Policies, ICRA 2024

## Summary

This paper studies how a real robot can learn pursuit-evasion behavior from onboard visual sensing under partial observability. The setting is strategically interesting because success depends not only on following dynamics, but also on inferring the evader's intent and acting under uncertainty.

For this vault, the paper is useful as adjacent embodied-robotics context: it shows how learned policies can produce strategic interactive behavior on physical hardware even when sensing is incomplete and the opponent is not directly predictable.

## Method

The core idea is to transform a hard partially observable pursuit-evasion problem into a supervised-learning problem. A fully observable policy acts as a teacher and generates supervision for a partially observable visual policy deployed on the real robot.

The paper argues that the quality of this supervision depends strongly on:

- how diverse versus optimal the evader behavior is,
- and how strong the modeling assumptions are inside the fully observable teacher.

The deployed robot uses an RGB-D camera and learns to combine pursuit, information gathering, and interception behavior from visual observations.

## Evaluation

The work is evaluated on physical quadruped pursuit-evasion interactions in the wild. The authors emphasize that the learned pursuer does more than chase reactively: when uncertain, it slows down or gathers information; when confident, it predicts and intercepts.

That makes the paper a nice example of embodied strategic behavior emerging from partial observability rather than from a hand-built state-estimation-and-planning stack.

## Notes / Critique

The strongest contribution is the framing trick: a difficult interactive RL problem is made more tractable by supervising the partially observable policy with a stronger fully observable one.

Its main limitation for this vault is domain distance. This is not a racing paper, and the dynamics are less extreme than elite drone racing or motorsport. Still, it connects well to [[real_world_robotic_reinforcement_learning]], [[Highly_dynamic_autonomous_system]], and [[embodied_autonomous_intelligence]] as a concrete example of strategic embodied interaction under uncertainty.

## Pages Created From This Source

- [[learning_vision_based_pursuit_evasion_robot_policies]]
- [[pursuit_evasion_robotics]]
