---
tags: [paper]
date: 2026-05-26
task: robotics
venue: "IEEE Robotics and Automation Letters (RA-L) 2024"
sources: 1
year: "2024"
doi: "10.1109/LRA.2024.3459797"
url: "https://doi.org/10.1109/LRA.2024.3459797"
topic:
  - Highly_dynamic_autonomous_system
  - real_world_robotic_reinforcement_learning
  - quadrupedal_locomotion
tech_backbone: [reinforcement_learning]
tech_representation: [perceptive_locomotion]
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: [pie]
hardware_used: [quadrupeds]
simulators_used: []
---

# PIE: Parkour with Implicit-Explicit Learning Framework for Legged Robots

> PIE: Parkour with Implicit-Explicit Learning Framework for Legged Robots | IEEE Robotics and Automation Letters (RA-L) 2024 | Shixin Luo, Songbo Li, Ruiqi Yu, Zhicheng Wang, Jun Wu, and Qiuguo Zhu | DOI: 10.1109/LRA.2024.3459797

## Summary

This paper asks how a quadruped can perform agile parkour on difficult terrain when both perception and actuation are unreliable.

Its answer is [[pie]], a one-stage end-to-end parkour framework based on implicit-explicit learning.

## Method

The training backbone is [[reinforcement_learning]].

The central systems contribution is [[pie]].

From the public abstract and title-level record, PIE:

- uses dual-level implicit-explicit estimation,
- keeps the training pipeline relatively simple,
- and targets zero-shot real-world transfer with noisy egocentric depth sensing.

For this vault, the important systems lesson is that agile legged parkour may benefit from keeping both latent and explicit state/terrain understanding in the loop rather than leaning entirely on one style of estimation.

## Key Results

The public record reports successful zero-shot deployment on a low-cost quadruped robot equipped with an unreliable egocentric depth camera, with strong performance on challenging real-world parkour terrain.

The most useful vault takeaway is broader than one obstacle family:

**quadruped parkour can be framed as an end-to-end learning problem that still preserves enough explicit structure to remain useful under noisy real sensing.**

## Hardware Used

- [[quadrupeds]]

## Related Work

This paper belongs near [[robot_parkour_learning]], but it appears more explicitly organized around implicit-explicit estimation rather than around one broad parkour repertoire alone.

Compared with [[learning_robust_perceptive_locomotion_for_quadrupedal_robots_in_the_wild]], it is more parkour- and obstacle-centric than terrain-robust locomotion-centric.

Compared with [[perceptive_locomotion_through_nonlinear_model_predictive_control]], it gives the learning-heavy alternative to embedding terrain understanding directly into online optimization.

It also belongs near [[perceptive_locomotion]], because the whole point is to make noisy perception directly useful for control before contact, not just to collect images for a downstream module.

## Notes / Critique

The strongest contribution is the architectural balance. PIE does not simply say "use more perception" or "use a bigger policy"; it argues that agile traversal needs the right mixture of implicit and explicit estimation.

The main caveat is that this ingest is anchored to a clean public abstract/title-level record rather than a rich local full-text parse. So I’ve kept the note focused on the method's reliable high-level structure.
