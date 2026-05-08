---
tags: [paper]
date: 2026-05-08
task: ai_theory
venue: "International Conference on Learning Representations"
sources: 1
year: "2025"
topic:
  - foundation_models_for_intelligent_decision_making
  - era_of_experience
tech_backbone: []
tech_representation: []
tech_generation: [compositional_reasoning_limits_in_sequence_models]
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
simulators_used: []
---

# Limits of Deep Learning: Sequence Modeling Through the Lens of Complexity Theory

> Limits of Deep Learning: Sequence Modeling Through the Lens of Complexity Theory | ICLR 2025 | Nikola Zubic, Federico Solda, Aurelio Sulser, and Davide Scaramuzza

## Summary

This paper investigates why modern sequence models still struggle with tasks that require dependable compositional reasoning. The focus is on function composition and related tasks that demand multi-step internal state tracking rather than surface pattern matching.

The central claim is that current deep-learning architectures face not just training difficulties but deeper computational limitations rooted in their representational capacity.

## Method

The paper studies structured state space models (`SSMs`) and connects them to the broader sequence-model landscape, including Transformers.

Its main approach is twofold:

- a complexity-theoretic analysis of what such models can and cannot compute efficiently,
- and an empirical evaluation on reasoning-heavy sequence tasks.

The theoretical results show that one-layer SSMs cannot efficiently perform function composition over large domains without impractically large state sizes, and that even multi-layer finite-precision SSMs remain limited in ways closely tied to weak computational classes.

The authors then argue that because SSMs and Transformers are closely related in expressivity, these failures illuminate broader deep-learning limits in sequence reasoning.

## Key Results

Empirically, the paper evaluates models on:

- function composition,
- multi-digit multiplication,
- dynamic programming,
- and Einstein-style logic puzzles.

Across these tasks, the paper reports strong degradation as compositional depth increases. Even with Chain-of-Thought prompting, models often fail to produce stable multi-step reasoning and instead rely on brittle shortcuts whose errors compound downstream.

The main message is not that prompting never helps, but that prompting does not erase the underlying computational bottlenecks.

## Related Work

For this vault, the paper fits best as a corrective or limiting perspective on [[foundation_models_for_intelligent_decision_making]] and [[era_of_experience]]. Those pages point toward richer, more general decision systems; this paper reminds us that current sequence models may still be fundamentally weak at the kind of compositional reasoning those systems would need.

It also complements [[foundation_models_and_intelligent_decision_making_progress_challenges_and_perspectives]] by sharpening one concrete challenge: broad multimodal priors are not the same thing as reliable multi-step reasoning.

## Notes / Critique

The strongest part of the paper is that it refuses the easy story that reasoning failures are only about insufficient scale or insufficient prompting. By tying failures to computational structure, it raises the bar for what a real solution would need to change.

The main caveat is scope. The paper studies reasoning through stylized tasks and model classes, so its conclusions should be read as a strong warning about current architectures rather than a complete theory of every large-model failure.
