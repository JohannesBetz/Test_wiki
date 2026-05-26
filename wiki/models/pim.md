---
tags: [model]
date: 2026-05-26
sources: 1
---

# PIM

## What It Is

`PIM` (Perceptive Internal Model) is a perceptive humanoid locomotion framework that embeds robot-centered elevation mapping directly into the state predictor loop to enable zero-shot sim-to-real transfer.

## Why It Matters

This system matters because it provides the humanoid robotics branch with a highly efficient, single-stage training method that handles fine-grained footholds (such as continuous stairs) while running on physical hardware with distinct joint configurations.

For this vault, PIM is useful as a model/system anchor for:
- Perceptive state prediction using combined elevation-history vectors.
- Low-overhead elevation map querying in simulator training.
- Gait-symmetry regularization and action curricula for humanoid control.
- Cross-platform zero-shot transfer (tested on Unitree H1 and Fourier GR-1).

## Representative Paper

- [[learning_humanoid_locomotion_with_perceptive_internal_model]]

## Relationship to the Wiki

This page belongs naturally near [[hybrid_internal_model]], [[perceptive_locomotion]], and [[humanoids]].

It directly complements proprioception-only architectures like [[hybrid_internal_model]] by showing how exteroception can be integrated directly into the predictor model rather than handled via separate mapping pipelines.

## Notes

PIM demonstrates that by using a grid of 96 sampled points, a humanoid robot can perform precise foot-step coordination (overcoming the foot length constraint vs stair width constraint) with an over 90% success rate on stairs of $\ge 0.15\text{m}$ height.
