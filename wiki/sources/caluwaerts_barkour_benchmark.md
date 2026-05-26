---
tags: [source]
date: 2026-05-24
sources: 1
---

# Caluwaerts Barkour Benchmark Source

> Source: `raw/pdfs/Calewerts_Barkour_Benchmark.pdf`
> Paper: Barkour: Benchmarking Animal-level Agility with Quadruped Robots, arXiv 2023

## Summary

This paper introduces `Barkour`, a benchmark for measuring quadruped agility through an obstacle course inspired by dog-agility competitions.

For this vault, the paper matters because it gives the quadruped branch a rare shared evaluation scaffold rather than only another control result.

## Method

From the paper record and abstract support, Barkour defines:

- a compact obstacle course with diverse agility demands,
- a time-based score with penalties inspired by dog agility competitions,
- and strong baseline solutions built from specialist skills and a Transformer-based generalist locomotion policy.

For this vault, the important point is that the paper is not only about how one controller works. It is about how agility itself should be measured across hardware and control approaches.

## Evaluation

The public record reports two baseline solution families:

- specialist locomotion skills paired with a higher-level navigation controller,
- and a distilled Transformer-based generalist locomotion policy named `Locomotion-Transformer`.

The reported hardware demonstration uses a custom-built quadruped robot, with performance still below real-dog agility but clearly inside the animal-inspired benchmarking frame.

## Notes / Critique

The strongest contribution is the benchmark itself. It gives the quadruped branch a structured way to talk about agility that is broader than speed alone.

That makes it a strong complement to:

- [[rapid_locomotion_via_reinforcement_learning]], which shows fast learned locomotion,
- [[robot_parkour_learning]], which shows multi-skill obstacle traversal,
- and [[agile_but_safe_learning_collision_free_high_speed_legged_locomotion]], which emphasizes safe high-speed behavior in clutter.

## Pages Created From This Source

- [[barkour_benchmarking_animal_level_agility_with_quadruped_robots]]
- [[barkour]]
