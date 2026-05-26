---
tags: [model]
date: 2026-05-26
sources: 1
---

# PARC

## What It Is

`PARC` is a physics-based augmentation framework that uses reinforcement learning and simulation to iteratively expand motion datasets for agile terrain-traversal controllers.

## Why It Matters

This system matters because it attacks a different bottleneck than many locomotion papers in the vault.

Instead of only asking how to design a better controller, PARC asks how to grow the motion experience available to that controller when agile demonstrations are scarce.

## Representative Paper

- [[parc_physics_based_augmentation_with_reinforcement_learning_for_character_controllers]]

## Relationship to the Wiki

This page belongs naturally near [[quadrupedal_locomotion]], [[reinforcement_learning]], and [[Highly_dynamic_autonomous_system]].

It also complements other structure-adding ideas in the vault such as [[adversarial_motion_priors]], [[motion_matching]], and [[sim_to_real_transfer]].

## Notes

PARC is a good fit for this vault because it makes a useful methodological point: sometimes the missing ingredient in agile control is not one more reward term or one more controller trick, but a better way to expand the movement data the policy can learn from.
