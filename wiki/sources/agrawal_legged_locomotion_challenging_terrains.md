---
tags: [source]
date: 2026-05-22
sources: 1
---

# Agrawal Legged Locomotion Challenging Terrains Source

> Source: `raw/pdfs/Agrawal_LeggedLocomotion_Challenging_Terrains.pdf`
> Paper: Legged Locomotion in Challenging Terrains using Egocentric Vision, CoRL 2023

## Summary

This paper studies how a quadruped can use onboard egocentric vision to traverse challenging terrain without relying on privileged external mapping or narrowly scripted foothold logic.

For this vault, the paper matters because it strengthens the perceptive-locomotion branch with a compact, low-cost, vision-first quadruped result.

## Method

The training backbone is [[reinforcement_learning]].

From the publication record and abstract support, the controller uses egocentric visual input to guide locomotion over varied terrain, with the learned policy handling both locomotion and terrain interpretation in one embodied loop.

For this vault, the important point is that the paper pushes perception directly into the locomotion policy rather than treating terrain understanding as a separate planning layer.

## Evaluation

The public record reports traversal over a broad variety of challenging terrains, with robustness to perturbations such as pushes, slippery surfaces, and rocky ground.

For this vault, the useful takeaway is broader than one benchmark:

small resource-constrained quadrupeds can use egocentric vision to achieve terrain-aware locomotion competence that would otherwise require heavier mapping or more hand-structured terrain reasoning.

## Notes / Critique

The strongest contribution is the combination of embodiment realism and perceptual simplicity: a robot with egocentric vision can still move capably through quite messy terrain.

That makes it a strong complement to:

- [[learning_robust_perceptive_locomotion_for_quadrupedal_robots_in_the_wild]], which pushes a more map-centric perceptive locomotion story,
- [[rma_rapid_motor_adaptation_for_legged_robots]], which emphasizes latent adaptation without making vision central,
- and [[agile_but_safe_learning_collision_free_high_speed_legged_locomotion]], which emphasizes safety-aware policy switching in clutter.

## Pages Created From This Source

- [[legged_locomotion_in_challenging_terrains_using_egocentric_vision]]
