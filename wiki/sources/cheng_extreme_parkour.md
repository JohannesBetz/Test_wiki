---
tags: [source]
date: 2026-05-26
sources: 1
---

# Cheng Extreme Parkour Source

> Source: `raw/pdfs/Cheng_Extreme_Parkour.pdf`
> Paper: Extreme Parkour with Legged Robots, arXiv 2023

## Summary

This paper studies how a small low-cost quadruped can perform highly dynamic parkour behaviors despite imprecise actuation and noisy egocentric depth sensing.

For this vault, it matters because it sharpens a very specific claim: extreme agility does not necessarily require a high-end robot and a heavy classical perception stack if large-scale RL can learn sufficiently precise end-to-end behavior.

## Method

The training backbone is [[reinforcement_learning]].

The paper uses a single neural network policy operating directly from a front-facing depth image.

For this vault, the important point is that the system treats parkour as an end-to-end sensorimotor learning problem under deliberately imperfect hardware rather than as a carefully engineered lab-grade stack.

## Evaluation

The public record reports high jumps over obstacles roughly twice the robot's height, long jumps across gaps roughly twice its body length, handstands, tilted-ramp traversal, and generalization to novel obstacle courses.

The broader takeaway is that extreme quadruped parkour can emerge from learning even when sensing and actuation are visibly low quality by traditional robotics standards.

## Notes / Critique

The strongest contribution is the hardware realism. This paper is useful because it argues that `low-cost and imprecise` does not automatically mean `incapable of extreme agility`.

That makes it a natural complement to:

- [[robot_parkour_learning]], which emphasizes multi-skill quadruped parkour under one policy,
- [[pie_parkour_with_implicit_explicit_learning_framework_for_legged_robots]], which emphasizes implicit-explicit estimation under noisy sensing,
- and [[learning_visual_parkour_from_generated_images]], which emphasizes sim-to-real visual transfer for parkour.

## Pages Created From This Source

- [[extreme_parkour_with_legged_robots]]
