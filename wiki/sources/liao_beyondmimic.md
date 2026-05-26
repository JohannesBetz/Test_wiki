---
tags: [source]
date: 2026-05-26
sources: 1
---

# Liao BeyondMimic Source

> Source: `raw/pdfs/Liao_BeyondMimic.pdf`
> Paper: BeyondMimic: From Motion Tracking to Versatile Humanoid Control via Guided Diffusion, arXiv 2025

## Summary

This paper studies how humanoid control can move beyond narrow motion imitation and tracking toward more versatile whole-body behavior.

For this vault, it matters because it explicitly frames the transition from `mimic` to `versatile humanoid control` as the core problem, and does so through guided diffusion rather than only through direct policy learning.

## Method

The paper centers on [[beyondmimic]], a guided-diffusion approach for versatile humanoid control.

From the local metadata, the important framing is:

- starting from motion tracking,
- extending toward more versatile humanoid control,
- and using guided diffusion as the central mechanism.

For this vault, the key point is that BeyondMimic treats motion tracking as a starting point rather than an end state for humanoid capability.

## Evaluation

The metadata supports placing the paper in the humanoid guided-diffusion / whole-body-control branch.

The broader takeaway is that humanoid motion imitation is increasingly being reframed as a substrate for broader control versatility rather than a terminal benchmark.

## Notes / Critique

The strongest contribution appears to be the conceptual reframing. BeyondMimic is useful because it says, in effect, that tracking alone is not enough; the real goal is versatile whole-body control.

That makes it a natural complement to:

- [[sonic_supersizing_motion_tracking_for_natural_humanoid_whole_body_control]], which scales motion tracking,
- [[kungfubot_physics_based_humanoid_whole_body_control_for_learning_highly_dynamic_skills]], which pushes expressive high-dynamic imitation,
- and [[dreamcontrol_human_inspired_whole_body_humanoid_control_for_scene_interaction_via_guided_diffusion]], which pushes guided diffusion into scene interaction.

## Pages Created From This Source

- [[beyondmimic_from_motion_tracking_to_versatile_humanoid_control_via_guided_diffusion]]
- [[beyondmimic]]
