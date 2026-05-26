---
tags: [paper]
date: 2026-05-26
task: robotics
venue: "ACM SIGGRAPH 2025"
sources: 1
year: "2025"
doi: "10.1145/3721238.3730710"
url: "https://arxiv.org/abs/2505.04002"
topic:
  - Highly_dynamic_autonomous_system
  - quadrupedal_locomotion
tech_backbone: [reinforcement_learning]
tech_representation: []
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: [parc]
hardware_used: [quadrupeds]
simulators_used: []
---

# PARC: Physics-based Augmentation with Reinforcement Learning for Character Controllers

> PARC: Physics-based Augmentation with Reinforcement Learning for Character Controllers | ACM SIGGRAPH 2025 | Michael Xu, Yi Shi, KangKang Yin, and Xue Bin Peng | arXiv 2505.04002

## Summary

This paper asks how agile terrain-traversal controllers can be learned when high-quality motion data for parkour-like behaviors is too limited to cover the full skill space directly.

Its answer is [[parc]], a framework that uses physics-based augmentation together with [[reinforcement_learning]] to iteratively expand traversal capabilities.

## Method

The training backbone is [[reinforcement_learning]].

The central systems contribution is [[parc]].

From the project page and public abstract support, PARC starts from a small dataset of core terrain-traversal skills, trains a motion generator, then uses simulation and learning to iteratively augment the motion data and improve the traversal controller.

For this vault, the important systems lesson is that some agility bottlenecks may come not from the controller architecture alone, but from the narrowness of the motion data available to define the behavior space.

## Key Results

The public record supports the main claim that PARC expands the capabilities of terrain-traversal character controllers beyond what a small fixed seed dataset can support.

The most useful vault takeaway is broader than one benchmark:

**agile locomotion can be improved not only by better controllers, but by better procedures for growing the motion dataset those controllers learn from.**

## Hardware Used

- [[quadrupeds]]

## Related Work

This paper belongs near [[quadrupedal_locomotion]], but as a simulation-side capability-expansion paper rather than a direct real-hardware deployment result.

Compared with [[learning_robust_and_agile_legged_locomotion_using_adversarial_motion_priors]], it adds structure through dataset growth rather than through a learned prior over motion quality.

Compared with [[animal_gaits_on_quadrupedal_robots_using_motion_matching_and_model_based_control]], it is less about retrieving from a fixed motion library and more about enlarging the motion library itself through physics-based augmentation.

Compared with [[learning_visual_parkour_from_generated_images]], it is less about generated perception and more about generated motion experience for traversal.

## Notes / Critique

The strongest contribution is that it reframes scarce agile motion data as something the learning loop can actively expand instead of passively accepting as fixed.

The main caveat is that this is still a simulation-side paper about character controllers and terrain traversal in physics-based environments. So I’ve linked it as an important adjacent framework for agility learning rather than presenting it as evidence of the same real-world maturity as the strongest deployed robot papers in the vault.
