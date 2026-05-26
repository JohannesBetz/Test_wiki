---
tags: [source]
date: 2026-05-22
sources: 1
---

# Wu Humanoid Parkour Source

> Source: `raw/pdfs/WU_Humanoid_Parkour.pdf`
> Paper: Perceptive Humanoid Parkour: Chaining Dynamic Human Skills via Motion Matching, arXiv 2026

## Summary

This paper studies how a humanoid can perform dynamic parkour-like traversal by chaining multiple high-agility human-inspired skills rather than relying on one monolithic locomotion mode.

For this vault, the paper matters because it brings the highly dynamic branch decisively into humanoid terrain, where perception, skill composition, and recovery all interact under much harsher embodiment constraints than standard flat-ground walking.

## Method

The core idea is [[motion_matching]].

From the title and metadata, the system appears to combine:

- perceptive scene understanding,
- a library of dynamic human-like motion skills,
- and motion-matching-based selection or chaining of those skills during execution.

For this vault, the important point is architectural: the controller is framed not only as a continuous low-level policy, but as a mechanism for composing reusable dynamic skills under perception.

## Evaluation

According to the public metadata and project references embedded in the PDF, the method targets perceptive humanoid parkour with dynamic skill chaining and real-world validation.

For this vault, the useful takeaway is broader than one benchmark result: highly dynamic embodied competence may depend not only on learning one agile controller, but on learning how to transition among many agile behaviors without losing balance or situational awareness.

## Notes / Critique

The strongest contribution is the emphasis on chaining. That pushes the discussion beyond isolated locomotion tricks toward sequential embodied agility.

That makes it a strong complement to:

- [[attention_based_map_encoding_for_learning_generalized_legged_locomotion]], which emphasizes generalized perceptive terrain encoding,
- [[perceptive_locomotion_through_nonlinear_model_predictive_control]], which emphasizes structured model-based perceptive control,
- and [[Highly_dynamic_autonomous_system]], where this paper adds a humanoid example of dynamic embodied skill composition.

## Pages Created From This Source

- [[perceptive_humanoid_parkour_chaining_dynamic_human_skills_via_motion_matching]]
- [[motion_matching]]
