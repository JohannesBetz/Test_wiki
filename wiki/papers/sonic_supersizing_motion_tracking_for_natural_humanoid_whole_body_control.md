---
tags: [paper]
date: 2026-05-26
task: robotics
venue: "arXiv 2025"
sources: 1
year: "2025"
doi: "10.48550/arXiv.2511.07820"
url: "https://doi.org/10.48550/arXiv.2511.07820"
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
models_used: [sonic]
hardware_used: [humanoids]
simulators_used: []
---

# SONIC: Supersizing Motion Tracking for Natural Humanoid Whole-Body Control

> SONIC: Supersizing Motion Tracking for Natural Humanoid Whole-Body Control | arXiv 2025 | Zhengyi Luo, Ye Yuan, Tingwu Wang, Chenran Li, Fernando Castaneda, Sirui Chen, Zi-Ang Cao, Jiefeng Li, David Minor, Qingwei Ben, Jinhyung Park, David Sami, Zi Wang, Xingye Da, Runyu Ding, Cyrus Hogg, Lina Song, Edy Lim, Eugene Jeong, Tairan He, Haoru Xue, Wenli Xiao, Simon Yuen, Jan Kautz, Yan Chang, Umar Iqbal, Linxi "Jim" Fan, and Yuke Zhu | DOI: 10.48550/arXiv.2511.07820

## Summary

This paper asks how humanoid motion tracking can be enlarged enough to support natural whole-body control rather than only a narrow library of carefully chosen behaviors.

Its answer is [[sonic]], a motion-tracking framework for natural humanoid whole-body control.

## Method

The training backbone is [[reinforcement_learning]].

The central systems contribution is [[sonic]].

From the local metadata and public project record, the paper centers on:

- scaling up the scope of motion tracking,
- targeting natural whole-body humanoid behavior,
- and transferring the result onto the Unitree G1 humanoid.

For this vault, the important systems lesson is that motion tracking may be evolving from a specialized imitation trick into a broader organizing principle for humanoid whole-body control.

## Key Results

The local metadata directly links the paper to the Unitree G1 humanoid and a public project page, which supports placing it in the real-world humanoid branch.

The most useful vault takeaway is broader than one benchmark:

**natural humanoid whole-body control may depend not only on better low-level controllers, but on making the motion-tracking regime itself larger, more varied, and more transferable.**

## Hardware Used

- [[humanoids]]

## Related Work

This paper belongs near [[kungfubot_physics_based_humanoid_whole_body_control_for_learning_highly_dynamic_skills]], but it appears more explicitly centered on scaling motion tracking itself rather than on one specific expressive dynamic skill family.

Compared with [[agility_meets_stability_versatile_humanoid_control_with_heterogeneous_data]], it appears less about heterogeneous behavior-data unification in general and more about enlarging the motion-tracking foundation for natural control.

Compared with [[physhsi_towards_a_real_world_generalizable_and_natural_humanoid_scene_interaction_system]], it appears less scene-grounding-centric and more motion-prior and tracking centric.

It also belongs near [[Highly_dynamic_autonomous_system]], because expanding the set of trackable whole-body behaviors is one route toward more capable high-dynamic humanoid autonomy.

## Notes / Critique

The strongest contribution is the framing around scale. This paper suggests that one of the bottlenecks for humanoid naturalness is not simply better reward design, but the limited scope of what the motion-tracking substrate itself can express.

The main caveat is that this ingest is anchored to clean local PDF metadata and project-page support rather than a full local text parse. So I’ve kept the note at the level of reliable systems interpretation rather than fine implementation detail.
