---
tags: [paper]
date: 2026-05-26
task: robotics
venue: "arXiv 2025"
sources: 1
year: "2025"
doi: "10.48550/arXiv.2511.17373"
url: "https://doi.org/10.48550/arXiv.2511.17373"
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
models_used: []
hardware_used: [humanoids]
simulators_used: []
---

# Agility Meets Stability: Versatile Humanoid Control with Heterogeneous Data

> Agility Meets Stability: Versatile Humanoid Control with Heterogeneous Data | arXiv 2025 | Yixuan Pan, Ruoyi Qiao, Li Chen, Kashyap Chitta, Liang Pan, Haoguang Mai, Qingwen Bu, Hao Zhao, Cunyuan Zheng, Ping Luo, and Hongyang Li | DOI: 10.48550/arXiv.2511.17373

## Summary

This paper asks how a humanoid can remain versatile across agile and stable behaviors rather than being optimized only for one narrow control regime.

Its answer is a humanoid-control approach built around heterogeneous data.

## Method

The training backbone is [[reinforcement_learning]].

From the local metadata and public title-level record, the paper centers on:

- integrating heterogeneous behavior data,
- training one humanoid control stack across both agility and stability demands,
- and targeting a broader behavior envelope than single-regime humanoid controllers usually cover.

For this vault, the important systems lesson is that humanoid competence may broaden not only through bigger models or more reward tuning, but through more varied data support for one shared controller.

## Key Results

The local metadata directly links the paper to the Unitree G1 humanoid, which supports placing it in the real-world humanoid branch.

The most useful vault takeaway is broader than one benchmark:

**humanoid control may become more generally useful when the training pipeline is designed to absorb heterogeneous behavior evidence instead of optimizing separately for each narrow skill regime.**

## Hardware Used

- [[humanoids]]

## Related Work

This paper belongs near [[real_world_humanoid_locomotion_with_reinforcement_learning]], but it shifts the emphasis from basic locomotion competence toward broader behavior coverage.

Compared with [[hub_learning_extreme_humanoid_balance]], it appears less narrowly focused on one low-margin balance regime and more focused on unifying several regimes under one controller.

Compared with [[kungfubot_physics_based_humanoid_whole_body_control_for_learning_highly_dynamic_skills]], it appears less centered on one expressive motion family and more on the data-side question of how versatile humanoid behavior should be trained.

Compared with [[physhsi_towards_a_real_world_generalizable_and_natural_humanoid_scene_interaction_system]], it appears less scene-grounding-centric and more controller-coverage-centric.

## Notes / Critique

The strongest contribution is the framing. This paper gives the vault a useful `agility versus stability is the wrong split` perspective, where the real goal is one controller supported by sufficiently heterogeneous evidence.

The main caveat is that this ingest is anchored to clean local metadata and title-level support rather than a full local text parse. So I’ve kept the note at the level of reliable systems interpretation rather than fine implementation detail.
