---
tags: [model]
date: 2026-05-26
sources: 1
---

# HumanPlus

## What It Is

`HumanPlus` is a full-stack humanoid system for shadowing human motion and learning autonomous skills from humans.

## Why It Matters

This system matters because it gives the humanoid branch a concrete `human data -> robot shadowing -> teleoperated collection -> autonomous imitation` pipeline rather than only isolated control results.

For this vault, HumanPlus is useful as a model/system anchor for:

- humanoid shadowing from RGB input,
- learning from human whole-body motion,
- teleoperation-assisted humanoid data collection,
- and autonomous skill imitation from egocentric demonstrations.

## Representative Paper

- [[humanplus_humanoid_shadowing_and_imitation_from_humans]]

## Relationship to the Wiki

This page belongs naturally near [[physhsi_towards_a_real_world_generalizable_and_natural_humanoid_scene_interaction_system]], [[sonic_supersizing_motion_tracking_for_natural_humanoid_whole_body_control]], and [[real_world_humanoid_locomotion_with_reinforcement_learning]].

It complements the other humanoid entries by focusing on how humanoids can acquire skill data from humans rather than only how they execute locomotion, balance, or parkour once trained.

## Notes

HumanPlus is a good fit for this vault because it sharpens a useful distinction: a humanoid system may need not only a good controller, but also a good route for converting abundant human behavior into useful robot-native data.
