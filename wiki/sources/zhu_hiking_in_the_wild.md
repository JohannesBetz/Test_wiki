---
tags: [source]
date: 2026-05-26
sources: 1
---

# Zhu Hiking in the Wild Source

> Source: `raw/pdfs/Zhu_Hiking_in-The-wild.pdf`
> Paper: Hiking in the Wild: A Scalable Perceptive Parkour Framework for Humanoids, arXiv 2026

## Summary

This paper studies how a humanoid can traverse complex outdoor terrain robustly enough that hiking becomes a perceptive whole-body control problem rather than only a flat-ground locomotion problem.

For this vault, the paper matters because it extends the humanoid parkour branch from discrete obstacle demos toward more open-ended wild-terrain traversal.

## Method

The training backbone is [[reinforcement_learning]].

From the arXiv record and project-page abstract support, the system uses a single-stage end-to-end policy that maps raw depth input and proprioception directly to joint actions without depending on external state-estimation pipelines.

Two design ideas stand out in the public description:

- a foothold-safety mechanism using terrain-edge detection and foot-volume points,
- and flat-patch sampling to reduce reward hacking while keeping navigation targets feasible.

For this vault, the important point is that the paper treats scalable perceptive hiking as a safety-and-representation problem, not only as a bigger parkour benchmark.

## Evaluation

The public record reports field experiments on a full-size humanoid across stairs, slopes, grassy ramps, gaps, and longer hiking-style traversals, with speeds up to 2.5 m/s.

For this vault, the useful takeaway is broader than one terrain set:

humanoid perceptive locomotion can become more deployable when the policy is trained to reason directly from raw depth and proprioception while explicitly protecting foothold validity.

## Notes / Critique

The strongest contribution is the way the paper pushes perceptive humanoid locomotion into messy unstructured outdoor settings without leaning on a heavier mapping stack.

That makes it a strong complement to:

- [[perceptive_humanoid_parkour_chaining_dynamic_human_skills_via_motion_matching]], which emphasizes dynamic skill composition,
- [[humanoid_parkour_learning]], which emphasizes one end-to-end parkour policy,
- and [[beamdojo_learning_agile_humanoid_locomotion_on_sparse_footholds]], which emphasizes precise foothold validity on sparse terrain.

## Pages Created From This Source

- [[hiking_in_the_wild_a_scalable_perceptive_parkour_framework_for_humanoids]]
