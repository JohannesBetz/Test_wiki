---
tags: [source]
date: 2026-05-20
sources: 1
---

# Wu On-Track System Identification Source

> Source: `raw/pdfs/WU_On_track_System_Identification.pdf`
> Paper: Vision-Augmented On-Track System Identification for Autonomous Racing via Attention-Based Priors and Iterative Neural Correction, arXiv 2026

## Summary

This paper studies autonomous-racing model learning from an on-track system-identification perspective. The title suggests a very specific goal: improve racing-relevant system identification by combining vision-based track or scene context with learned correction of the vehicle model itself.

That makes it relevant to the vault because it sits at a useful junction between:

- vehicle dynamics modeling,
- repeated-lap or on-track adaptation,
- and perception-aware control-relevant learning.

## Method

The central technique is best represented here as [[vision_augmented_system_identification]].

The paper title suggests three key ingredients:

- on-track system identification rather than purely offline fitting,
- attention-based priors that likely use visual context to shape model estimation,
- and iterative neural correction to refine the identified dynamics model over time.

This positions the paper as a control-aware model-learning approach rather than a purely predictive perception paper.

## Evaluation

At the vault level, the important question is whether visual track or scene cues can improve identification of the dynamics that actually matter for racing control, especially when the car is operating near the limit and nominal models become mismatched.

That places the paper near the branch of work that asks not only "can we fit the dynamics better?" but "can we identify the right dynamics quickly enough for racing use?"

## Notes / Critique

The main conceptual contribution is the idea that system identification for racing may benefit from visual priors about the local driving context, rather than relying only on internal vehicle telemetry and generic model structure.

The local metadata was clean enough to recover canonical title, authors, and arXiv DOI. I did not have a convenient full-text extraction path in this workspace, so this source note stays careful and method-level rather than pretending to reconstruct all experimental details.

## Pages Created From This Source

- [[vision_augmented_on_track_system_identification_for_autonomous_racing_via_attention_based_priors_and_iterative_neural_correction]]
- [[vision_augmented_system_identification]]
