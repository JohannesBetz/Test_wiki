---
tags: [paper]
date: 2026-05-26
task: robotics
venue: "arXiv"
sources: 1
year: "2026"
doi: "10.48550/arXiv.2601.07718"
url: "https://doi.org/10.48550/arXiv.2601.07718"
topic:
  - Highly_dynamic_autonomous_system
  - embodied_autonomous_intelligence
  - real_world_robotic_reinforcement_learning
tech_backbone: [reinforcement_learning]
tech_representation: [perceptive_locomotion]
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
hardware_used: [humanoids]
simulators_used: []
---

# Hiking in the Wild: A Scalable Perceptive Parkour Framework for Humanoids

> Hiking in the Wild: A Scalable Perceptive Parkour Framework for Humanoids | arXiv 2026 | Shaoting Zhu, Ziwen Zhuang, Mengjie Zhao, Kun-Ying Lee, and Hang Zhao | DOI: 10.48550/arXiv.2601.07718

## Summary

This paper asks how a humanoid can move robustly through complex unstructured outdoor terrain where reactive locomotion alone is no longer enough and perception must guide safe foothold decisions.

Its answer is an end-to-end perceptive parkour framework that maps raw depth and proprioception directly to action while explicitly protecting foothold safety.

## Method

The training backbone is [[reinforcement_learning]].

The paper belongs directly in the [[perceptive_locomotion]] branch.

From the public abstract and project description, the policy is trained end-to-end without relying on external state-estimation or mapping infrastructure at deployment time.

Two especially important mechanisms are highlighted:

- terrain-edge-aware foothold safety using foot-volume reasoning,
- and flat-patch sampling to keep target selection feasible and reduce reward hacking.

For this vault, the important systems lesson is that humanoid hiking becomes tractable when perception, foothold safety, and action generation are treated as one scalable policy-design problem.

## Key Results

The public record reports field experiments on a full-size humanoid across stairs, slopes, gaps, grassy ramps, high platforms, and long-duration outdoor traversal, with speeds up to 2.5 m/s.

The most useful vault takeaway is broader than one hiking route:

**humanoid wild-terrain locomotion can be made more robust by combining direct depth-to-action perception with explicit foothold-safety mechanisms instead of leaning on brittle external mapping pipelines.**

## Hardware Used

- [[humanoids]]

## Related Work

This paper belongs near [[perceptive_humanoid_parkour_chaining_dynamic_human_skills_via_motion_matching]], but it is less about composing a library of dynamic skills and more about scaling perceptive locomotion to harder outdoor terrain.

Compared with [[humanoid_parkour_learning]], it appears less centered on multi-skill obstacle coverage as a unified parkour showcase and more centered on robust deployment in unstructured environments.

Compared with [[beamdojo_learning_agile_humanoid_locomotion_on_sparse_footholds]], it shifts the emphasis from sparse precise supports to broader wild-terrain foothold safety and hiking robustness.

It also belongs near [[Highly_dynamic_autonomous_system]], because it asks a hard version of the same question the vault keeps circling: how much perception can a fast embodied system use directly before the perception stack itself becomes the new fragility?

## Notes / Critique

The strongest contribution is the way it turns humanoid hiking into a scalable perceptive control problem rather than treating each terrain type as a separate special case.

The main caveat is that this ingest is anchored to the arXiv record and project-page abstract support rather than a clean full-text parse of the local PDF. So I’ve written it as a careful systems-level placement rather than pretending we have every ablation or implementation detail pinned down.
