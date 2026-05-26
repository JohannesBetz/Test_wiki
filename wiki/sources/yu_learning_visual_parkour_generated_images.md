---
tags: [source]
date: 2026-05-26
sources: 1
---

# Yu Learning Visual Parkour from Generated Images Source

> Source: `raw/pdfs/Yu_Learning Visual Parkour from Generated Images.pdf`
> Paper: Learning Visual Parkour from Generated Images, CoRL 2024

## Summary

This paper studies how a quadruped can learn visual parkour from RGB-only observations without requiring real-world visual training data or depth sensing.

For this vault, the paper matters because it gives the quadruped branch a strong generated-visual-data route into sim-to-real parkour.

## Method

The training backbone is [[reinforcement_learning]] with a strong [[sim_to_real_transfer]] emphasis.

From the CoRL record and abstract support, the key system contribution is a generative simulation pipeline that synthesizes diverse, physically accurate egocentric image sequences for training.

For this vault, the important point is that the visual training distribution is itself learned or generated rather than only randomized in conventional simulator space.

## Evaluation

The public record reports zero-shot transfer from simulation to a real robot using RGB-only observations from a low-cost camera.

For this vault, the useful takeaway is broader than one parkour demo:

generated visual worlds can become part of the transfer pipeline, not only a convenience for offline data augmentation.

## Notes / Critique

The strongest contribution is the way the paper treats perceptual realism as a trainable systems problem rather than as a fixed simulator limitation.

That makes it a strong complement to:

- [[legged_locomotion_in_challenging_terrains_using_egocentric_vision]], which is also vision-first but not built around generated-image simulation,
- [[robot_parkour_learning]], which emphasizes multi-skill obstacle traversal,
- and [[learning_robust_perceptive_locomotion_for_quadrupedal_robots_in_the_wild]], which approaches terrain perception through a different sim-to-real structure.

## Pages Created From This Source

- [[learning_visual_parkour_from_generated_images]]
- [[lucidsim]]
