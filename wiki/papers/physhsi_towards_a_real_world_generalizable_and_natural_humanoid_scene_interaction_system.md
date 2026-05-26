---
tags: [paper]
date: 2026-05-26
task: robotics
venue: "arXiv 2025"
sources: 1
year: "2025"
doi: "10.48550/arXiv.2510.11072"
url: "https://doi.org/10.48550/arXiv.2510.11072"
topic:
  - Highly_dynamic_autonomous_system
  - embodied_autonomous_intelligence
  - real_world_robotic_reinforcement_learning
tech_backbone: [reinforcement_learning]
tech_representation: [adversarial_motion_priors, sim_to_real_transfer]
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: [physhsi]
hardware_used: [humanoids]
simulators_used: []
---

# PhysHSI: Towards a Real-World Generalizable and Natural Humanoid-Scene Interaction System

> PhysHSI: Towards a Real-World Generalizable and Natural Humanoid-Scene Interaction System | arXiv 2025 | Huayi Wang, Wentao Zhang, Runyi Yu, Tao Huang, Junli Ren, Feiyu Jia, Zirui Wang, Xiaojie Niu, Xiao Chen, Jiahe Chen, Qifeng Chen, Jingbo Wang, and Jiangmiao Pang | DOI: 10.48550/arXiv.2510.11072

## Summary

This paper asks how a humanoid can achieve more natural and generalizable interaction with real scenes rather than only solving isolated locomotion or motion-imitation benchmarks.

Its answer is [[physhsi]], a real-world humanoid-scene interaction system.

## Method

The training backbone is [[reinforcement_learning]].

The central systems contribution is [[physhsi]].

From the local metadata and public project record, the system combines:

- AMP-style policy learning from motion priors,
- sim-to-real robustness training,
- and a real deployment stack that grounds the humanoid in scene perception and localization.

For this vault, the important systems lesson is that natural humanoid behavior in real scenes is not only a policy-learning question. It depends on how motion priors, embodiment, sensing, and deployment scaffolding are joined into one stack.

## Key Results

The public record reports real-world deployment on the Unitree G1 humanoid and positions the system as a step toward more generalizable natural humanoid-scene interaction.

The most useful vault takeaway is broader than one benchmark:

**humanoid autonomy is expanding from locomotion and parkour toward whole-body scene interaction, and that expansion appears to require both learned motor priors and a carefully grounded real-world systems stack.**

## Hardware Used

- [[humanoids]]

## Related Work

This paper belongs near [[real_world_humanoid_locomotion_with_reinforcement_learning]], but it shifts the emphasis from locomotion competence to broader humanoid-scene interaction.

Compared with [[humanoid_parkour_learning]], it appears less obstacle-centric and more oriented toward natural full-body behavior in everyday scenes.

Compared with [[kungfubot_physics_based_humanoid_whole_body_control_for_learning_highly_dynamic_skills]], it is less about expressive dynamic skill imitation and more about generalizable grounded interaction.

It also belongs near [[adversarial_motion_priors]], because its AMP-style motion-prior backbone reinforces the broader vault theme that learned motor structure can be as important as raw reward optimization.

## Notes / Critique

The strongest contribution is the systems ambition. This paper tries to move the humanoid story from isolated capability demos toward a more natural interaction regime where learning, embodiment, and perception all matter at once.

The main caveat is that this ingest is anchored to clean local PDF metadata and the public arXiv/project record rather than a full local text parse. So I’ve kept the note focused on the reliable system-level picture rather than fine implementation detail.
