---
tags: [source]
date: 2026-05-26
sources: 1
---

# Xu PARC Physics-Based RL Source

> Source: `raw/pdfs/XU_PARC_Physic_based-RL.pdf`
> Paper: PARC: Physics-based Augmentation with Reinforcement Learning for Character Controllers, SIGGRAPH 2025

## Summary

This paper studies how agile terrain-traversal skills can be expanded when motion-capture data for parkour-style behaviors is scarce and expensive to collect.

For this vault, the paper matters because it gives the legged/agility branch a simulation-side data-augmentation story rather than only another controller or reward-design story.

## Method

The training backbone is [[reinforcement_learning]].

From the project page and public abstract support, `PARC` iteratively augments motion datasets through a combination of:

- a motion generator trained on a small core traversal dataset,
- physics-based simulation,
- and reinforcement learning for terrain-traversal controllers.

For this vault, the important point is that the paper treats missing agility data as a system bottleneck that can itself be attacked algorithmically.

## Evaluation

The public record supports the main claim that PARC expands the capability of simulated terrain-traversal character controllers beyond what the small seed dataset alone would enable.

For this vault, the useful takeaway is broader than one simulated result:

physics-based augmentation can act as a bridge between scarce demonstration data and broader agile behavior coverage.

## Notes / Critique

The strongest contribution is the iterative augmentation idea. Instead of asking RL alone to discover everything from scratch, or motion data alone to cover every case, the framework lets generated physics-consistent experience enlarge the skill space.

That makes it a strong complement to:

- [[learning_robust_and_agile_legged_locomotion_using_adversarial_motion_priors]], which adds structure through learned motion priors,
- [[animal_gaits_on_quadrupedal_robots_using_motion_matching_and_model_based_control]], which adds structure through motion retrieval and model-based tracking,
- and [[learning_visual_parkour_from_generated_images]], which adds structure through generated visual training worlds.

## Pages Created From This Source

- [[parc_physics_based_augmentation_with_reinforcement_learning_for_character_controllers]]
- [[parc]]
