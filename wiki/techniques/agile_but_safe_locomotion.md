---
tags: [technique]
date: 2026-05-22
sources: 1
---

# Agile But Safe Locomotion

## Definition

Agile-but-safe locomotion is a learned control pattern in which fast aggressive motion and protective recovery behavior are treated as separate modes, with a learned safety estimator deciding when the system should switch between them.

## Key Approaches

In [[agile_but_safe_learning_collision_free_high_speed_legged_locomotion]], this pattern is implemented with three parts:

- an agile locomotion policy,
- a recovery policy,
- and a learned reach-avoid value network that governs switching and also shapes recovery behavior.

For this vault, the main point is that safety is not handled only through reward shaping or offline constraints. It is handled through an online decision about when the current control regime is no longer the right one.

## Representative Papers

- [[agile_but_safe_learning_collision_free_high_speed_legged_locomotion]]

## Open Problems

The most interesting open question is how general this pattern is across embodiments and environments. A learned safety switch can be powerful, but only if the value signal stays meaningful under distribution shift, sensor failures, or novel obstacle geometry.

Another sharp question for the vault is whether this idea scales beyond quadrupeds into racecars, drones, and humanoids, where the transition between aggressive and recovery behavior may be even more timing-critical and harder to interpret.
