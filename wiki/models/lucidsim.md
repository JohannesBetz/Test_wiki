---
tags: [model]
date: 2026-05-26
sources: 1
---

# LucidSim

## What It Is

`LucidSim` is a generated-image simulation pipeline used to create diverse, physically grounded egocentric RGB training sequences for quadruped parkour learning.

## Why It Matters

This system matters because it shifts part of the sim-to-real problem away from only policy robustness and toward the realism and diversity of the visual worlds used during training.

For this vault, that makes LucidSim a useful model/system anchor for:

- generated visual training data,
- RGB-only parkour transfer,
- and visually grounded high-dynamic locomotion.

## Representative Paper

- [[learning_visual_parkour_from_generated_images]]

## Relationship to the Wiki

This page belongs naturally near [[sim_to_real_transfer]], [[high_speed_perception]], and [[quadrupedal_locomotion]].

It also complements broader foundation-model discussions by showing a concrete robotics use case where generative models help shape the training world rather than directly output actions at deployment time.

## Notes

LucidSim is a nice fit for this vault because it gives a concrete answer to a recurring question: if simulation is too visually poor for real transfer, can generation improve the world model before the policy ever reaches the real robot?
