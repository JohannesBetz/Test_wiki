---
tags: [paper]
date: 2026-05-22
task: robotics
venue: "Conference on Robot Learning (CoRL) 2024"
sources: 1
year: "2024"
doi: ""
url: "https://openreview.net/forum?id=fs7ia3FqUM"
topic:
  - Highly_dynamic_autonomous_system
  - embodied_autonomous_intelligence
  - real_world_robotic_reinforcement_learning
tech_backbone: [reinforcement_learning]
tech_representation: []
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

# Humanoid Parkour Learning

> Humanoid Parkour Learning | Conference on Robot Learning (CoRL) 2024 | Ziwen Zhuang, Shenzhe Yao, and Hang Zhao | OpenReview: fs7ia3FqUM

## Summary

This paper asks whether one vision-based whole-body control policy can cover a meaningful range of humanoid parkour behaviors without relying on motion priors or one fixed optimized obstacle track.

Its answer is yes: a learned end-to-end visuomotor policy can support multiple parkour-like skills within one controller.

## Method

The paper uses [[reinforcement_learning]] as the training backbone for an end-to-end whole-body-control parkour policy.

From the available title, keywords, and abstract, the key design choice is not a narrow algorithmic trick but a unification move: the controller is trained to handle several obstacle-crossing behaviors within one visuomotor policy rather than as a collection of separately solved maneuvers.

For this vault, that makes the paper a good anchor for the `single-policy multi-skill humanoid agility` idea.

## Key Results

According to the public abstract, the policy enables a humanoid to jump onto elevated platforms, leap over hurdles, cross wide gaps, run in the wild, and traverse varied indoor and outdoor terrain while following joystick commands.

The most useful vault takeaway is broader than any one obstacle:

**humanoid parkour can be framed as one learned embodied-control problem instead of only as a set of isolated skill demos.**

## Hardware Used

- [[humanoids]]

## Related Work

This paper belongs directly near [[perceptive_humanoid_parkour_chaining_dynamic_human_skills_via_motion_matching]], but it represents a different design philosophy. The Wu paper emphasizes chaining dynamic skills through [[motion_matching]], while this paper emphasizes one end-to-end visuomotor parkour policy.

Compared with [[real_world_humanoid_locomotion_with_reinforcement_learning]], this paper pushes from robust locomotion into a much more aggressive traversal regime.

It also belongs near [[Highly_dynamic_autonomous_system]], because it gives the vault a stronger humanoid answer to the question of whether high-dynamic embodied autonomy really extends beyond locomotion into obstacle-rich agile motion.

## Notes / Critique

The strongest contribution is the single-policy multi-skill framing. It makes humanoid agility look less like a bag of tricks and more like a coherent learned capability.

The main caveat is that the current ingest is based on metadata, title, keywords, and public abstract support rather than a clean deep parse of the whole PDF text layer. So I’ve placed it as a careful high-level anchor in the humanoid agility branch rather than pretending we have every implementation detail pinned down.
