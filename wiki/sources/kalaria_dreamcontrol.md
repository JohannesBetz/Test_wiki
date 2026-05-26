---
tags: [source]
date: 2026-05-26
sources: 1
---

# Kalaria DreamControl Source

> Source: `raw/pdfs/Kalaria_DreamControl.pdf`
> Paper: DreamControl: Human-Inspired Whole-Body Humanoid Control for Scene Interaction via Guided Diffusion, arXiv 2025

## Summary

This paper studies how a humanoid can achieve human-inspired whole-body control for interacting with scenes rather than only for locomotion, parkour, or motion tracking in isolation.

For this vault, it matters because it gives the humanoid branch another `scene interaction` systems paper, but with a different flavor from the current RL- and motion-tracking-heavy entries: guided diffusion is used as the central control idea.

## Method

The paper centers on [[dreamcontrol]], a whole-body humanoid control system for scene interaction.

From the local PDF metadata and project-page support, the important framing is:

- human-inspired whole-body humanoid control,
- scene interaction as the target behavior,
- and guided diffusion as the key modeling/control ingredient.

For this vault, the key point is that DreamControl treats natural whole-body scene interaction as a generative-control problem rather than only a direct policy-learning or motion-tracking problem.

## Evaluation

The metadata and project record support placing the paper in the humanoid scene-interaction branch.

The broader takeaway is that humanoid control is increasingly exploring generative models as a route to richer, more human-like whole-body behavior in scenes.

## Notes / Critique

The strongest contribution appears to be the architectural shift: it asks whether guided diffusion can serve as a useful control prior for humanoid scene interaction.

That makes it a natural complement to:

- [[physhsi_towards_a_real_world_generalizable_and_natural_humanoid_scene_interaction_system]], which is also scene-interaction-centric but not diffusion-centered,
- [[sonic_supersizing_motion_tracking_for_natural_humanoid_whole_body_control]], which is more motion-tracking-centric,
- and [[humanplus_humanoid_shadowing_and_imitation_from_humans]], which is more focused on human-data pipelines.

## Pages Created From This Source

- [[dreamcontrol_human_inspired_whole_body_humanoid_control_for_scene_interaction_via_guided_diffusion]]
- [[dreamcontrol]]
