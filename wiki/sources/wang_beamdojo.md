---
tags: [source]
date: 2026-05-22
sources: 1
---

# Wang BeamDojo Source

> Source: `raw/pdfs/Wang_BeamDojo.pdf`
> Paper: BeamDojo: Learning Agile Humanoid Locomotion on Sparse Footholds, RSS 2025

## Summary

This paper studies how a humanoid can move agilely across sparse footholds, where success depends on precise stepping rather than only general balance or forward locomotion.

For this vault, the paper matters because it gives the humanoid branch a strong sparse-terrain result that sits between perceptive locomotion and high-dynamic whole-body control.

## Method

The core training backbone is [[reinforcement_learning]].

From the publication record and abstract, the system combines:

- a two-stage RL training pipeline,
- dense locomotion rewards together with sparse foothold-oriented rewards,
- and an onboard LiDAR-based elevation-map stack for deployment.

For this vault, the important point is that BeamDojo is not just another flat-ground humanoid locomotion result. It is explicitly about making perception and foot-placement precision matter under a harder terrain structure.

## Evaluation

The public record supports both simulation and real-world validation.

The main reported outcome is that BeamDojo enables agile humanoid locomotion with precise foot placement on sparse footholds while maintaining robustness under significant external disturbances.

For this vault, the key takeaway is broader than one benchmark:

humanoid agility can be pushed into foothold-constrained terrain if learning efficiency and terrain-grounded deployment perception are treated as part of the same system design problem.

## Notes / Critique

The strongest contribution is the way the paper connects sparse-reward agile locomotion with a concrete real-world terrain-perception stack.

That makes it a strong complement to:

- [[learning_robust_perceptive_locomotion_for_quadrupedal_robots_in_the_wild]], which develops a quadruped-side perceptive locomotion story,
- [[perceptive_locomotion_through_nonlinear_model_predictive_control]], which gives the model-based foothold-control counterpart,
- and [[humanoid_parkour_learning]], which emphasizes broader multi-skill parkour rather than sparse-foothold precision.

## Pages Created From This Source

- [[beamdojo_learning_agile_humanoid_locomotion_on_sparse_footholds]]
