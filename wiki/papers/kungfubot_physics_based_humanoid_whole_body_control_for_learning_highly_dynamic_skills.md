---
tags: [paper]
date: 2026-05-26
task: robotics
venue: "NeurIPS 2025"
sources: 1
year: "2025"
doi: "10.48550/arXiv.2506.12851"
url: "https://doi.org/10.48550/arXiv.2506.12851"
topic:
  - Highly_dynamic_autonomous_system
  - embodied_autonomous_intelligence
  - real_world_robotic_reinforcement_learning
tech_backbone: [reinforcement_learning]
tech_representation: [sim_to_real_transfer]
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: [kungfubot]
hardware_used: [humanoids]
simulators_used: []
---

# KungfuBot: Physics-Based Humanoid Whole-Body Control for Learning Highly-Dynamic Skills

> KungfuBot: Physics-Based Humanoid Whole-Body Control for Learning Highly-Dynamic Skills | NeurIPS 2025 | Weiji Xie, Jinrui Han, Jiakun Zheng, Huanyu Li, Xinzhe Liu, Jiyuan Shi, Weinan Zhang, Chenjia Bai, and Xuelong Li | DOI: 10.48550/arXiv.2506.12851

## Summary

This paper asks how a humanoid can learn and execute highly dynamic whole-body skills that go far beyond smooth walking or mild motion imitation, including expressive Kungfu and dance-like behaviors.

Its answer is [[kungfubot]], a physics-based humanoid whole-body control framework designed for highly dynamic skill learning.

## Method

The training backbone is [[reinforcement_learning]].

The central systems contribution is [[kungfubot]].

From the public abstract and project-page support, the framework uses:

- multi-step motion processing to make reference motions physically more feasible,
- adaptive motion tracking through a bi-level optimization formulation,
- and asymmetric actor-critic policy training for robust imitation.

For this vault, the important systems lesson is that highly dynamic humanoid skill learning may depend as much on how reference motions are cleaned and adapted as on how the final policy is optimized.

## Key Results

The public record reports significantly lower tracking error than prior approaches and successful deployment on the Unitree G1 humanoid with stable execution of highly dynamic motions.

The most useful vault takeaway is broader than one motion class:

**humanoid whole-body skill learning can be extended into highly dynamic expressive behaviors when the motion-retargeting and tracking pipeline is treated as part of the control problem.**

## Hardware Used

- [[humanoids]]

## Related Work

This paper belongs near [[hub_learning_extreme_humanoid_balance]], but it is more motion-imitation-centric and less narrowly focused on low-margin balance poses.

Compared with [[humanoid_parkour_learning]], it is less about terrain traversal and more about expressive high-dynamic motion tracking.

Compared with [[perceptive_humanoid_parkour_chaining_dynamic_human_skills_via_motion_matching]], it is less about selecting among skills online and more about making difficult reference motions trackable end to end.

It also belongs near [[Highly_dynamic_autonomous_system]], because it pushes the vault’s high-dynamics story beyond locomotion speed into whole-body motion expressiveness under physical constraints.

## Notes / Critique

The strongest contribution is the motion-processing pipeline. It gives the vault a cleaner example of how difficult human reference motions may need to be repaired and adapted before RL can use them productively on a humanoid body.

The main caveat is that this ingest is anchored to the arXiv/NeurIPS public record and project-page abstract support rather than a clean full-text parse of the local PDF. So I’ve kept the note focused on the reliable architectural picture rather than every implementation detail.
