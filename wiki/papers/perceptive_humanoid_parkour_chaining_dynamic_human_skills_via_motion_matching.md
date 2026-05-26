---
tags: [paper]
date: 2026-05-22
task: robotics
venue: "arXiv"
sources: 1
year: "2026"
doi: "10.48550/arXiv.2602.15827"
url: "https://doi.org/10.48550/arXiv.2602.15827"
topic:
  - Highly_dynamic_autonomous_system
  - embodied_autonomous_intelligence
tech_backbone: []
tech_representation: [motion_matching]
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

# Perceptive Humanoid Parkour: Chaining Dynamic Human Skills via Motion Matching

> Perceptive Humanoid Parkour: Chaining Dynamic Human Skills via Motion Matching | arXiv 2026 | Zhen Wu, Xiaoyu Huang, Lujie Yang, Yuanhang Zhang, Xi Chen, Pieter Abbeel, Rocky Duan, Angjoo Kanazawa, Carmelo Sferrazza, Guanya Shi, and C. Karen Liu | DOI: 10.48550/arXiv.2602.15827

## Summary

This paper asks how a humanoid can perform parkour-like traversal over challenging environments without relying on one narrow locomotion pattern.

Its answer is to chain dynamic human-inspired skills through a perceptive motion-selection mechanism built around [[motion_matching]].

## Method

The central idea is [[motion_matching]].

From the title and available metadata, the system uses perception to interpret upcoming terrain or obstacles, then selects or blends among dynamic motion skills rather than solving the whole behavior as one undifferentiated controller.

For this vault, the key systems lesson is that highly dynamic humanoid behavior may depend not only on stability and recovery, but on the ability to sequence different agile behaviors fluidly enough that the transitions themselves do not become the failure mode.

## Key Results

The metadata and linked project traces support the main high-level claim: the paper demonstrates perceptive humanoid parkour through chained dynamic skills rather than isolated locomotion primitives.

The most useful vault takeaway is broader than one stunt or terrain setup:

**humanoid high-dynamic autonomy may require compositional skill transitions, not only stronger single-skill controllers.**

## Hardware Used

- [[humanoids]]

## Related Work

This paper belongs directly near [[embodied_autonomous_intelligence]], where it strengthens the idea that embodiment matters not only through local balance control, but through the sequencing of whole-body skills under perception.

Compared with [[attention_based_map_encoding_for_learning_generalized_legged_locomotion]], this paper is less about generalized terrain encoding and more about dynamic skill composition on a humanoid body.

Compared with [[perceptive_locomotion_through_nonlinear_model_predictive_control]], it appears much less optimizer-centric and much more motion-library-centric.

It also belongs near [[Highly_dynamic_autonomous_system]], because humanoid parkour is a strong stress test for whether the vault's claims about speed, timing, perception, and dynamic-envelope management really extend beyond racecars, drones, and quadrupeds.

## Notes / Critique

The strongest contribution is conceptual: the paper treats parkour not as one skill, but as a chain of dynamically selected human-like skills.

The main caveat is that the current ingest is based on metadata, title, and local traces rather than a clean full-text extraction. So I’ve placed it as a careful architectural anchor in the humanoid/high-dynamics branch rather than pretending we have every experimental nuance in hand.
