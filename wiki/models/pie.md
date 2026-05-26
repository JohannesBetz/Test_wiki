---
tags: [model]
date: 2026-05-26
sources: 1
---

# PIE

## What It Is

`PIE` is a quadruped parkour framework based on implicit-explicit learning for agile traversal on difficult terrain.

## Why It Matters

This system matters because it gives the quadruped branch a concrete end-to-end parkour architecture that tries to balance agility with perception reliability rather than assuming either perfect terrain modeling or purely latent policy competence.

For this vault, PIE is useful as a model/system anchor for:

- quadruped parkour,
- dual-level implicit-explicit estimation,
- noisy egocentric depth-based traversal,
- and zero-shot transfer of agile obstacle behavior.

## Representative Paper

- [[pie_parkour_with_implicit_explicit_learning_framework_for_legged_robots]]

## Relationship to the Wiki

This page belongs naturally near [[robot_parkour_learning]], [[perceptive_locomotion]], and [[quadrupedal_locomotion]].

It complements the other quadruped entries by making the estimation structure itself part of the parkour story.

## Notes

PIE is a good fit for this vault because it sharpens a useful distinction: agile legged traversal is not only about having more skill diversity, but also about how the controller organizes uncertain knowledge about robot state and terrain.
