---
tags: [model]
date: 2026-05-26
sources: 1
---

# HuB

## What It Is

`HuB` is a humanoid-control framework for learning extreme balance skills such as single-leg poses and high-kick-style whole-body postures.

## Why It Matters

This system matters because it isolates balance as a central humanoid capability rather than treating it as a hidden subproblem of generic locomotion.

For this vault, HuB is useful as a model/system anchor for:

- extreme humanoid postural control,
- reference-motion refinement,
- balance-aware policy learning,
- and sim-to-real robustness for narrow-stability skills.

## Representative Paper

- [[hub_learning_extreme_humanoid_balance]]

## Relationship to the Wiki

This page belongs naturally near [[real_world_humanoid_locomotion_with_reinforcement_learning]], [[humanoid_parkour_learning]], and [[Highly_dynamic_autonomous_system]].

It complements the other humanoid pages by covering a more balance-centric regime than either ordinary locomotion or terrain traversal.

## Notes

HuB is a good fit for this vault because it sharpens a useful distinction: a humanoid may be able to walk, run, or traverse obstacles, yet still fail at the kind of extreme low-margin balance skills that reveal whether whole-body control is genuinely mature.
