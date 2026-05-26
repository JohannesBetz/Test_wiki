---
tags: [source]
date: 2026-05-13
sources: 1
---

# Bae Driver Training Source

> Source: `raw/pdfs/Bae_Data-Driven_Driver_Training_via_Counterfactual_and_Language-Based_Guidance_in_Racing_Scenarios.pdf`
> Paper: Data-Driven Driver Training via Counterfactual and Language-Based Guidance in Racing Scenarios, IEEE Access 2025

## Summary

This paper proposes an AI racing coach for human drivers. Instead of controlling the vehicle directly, the system analyzes corner-specific driving behavior, estimates skill level from telemetry-derived features, and gives personalized improvement advice in natural language.

For this vault, the paper is interesting because it sits right beside [[professional_race_driver_expertise]]: rather than asking how to replace the driver, it asks how to help a novice driver learn expert-like racing behavior more quickly and more systematically.

## Method

The framework is fully data-driven and has three main stages:

- unsupervised clustering of sequential driving behavior to create pseudo skill labels,
- supervised classification of corner performance using racing-critical features,
- and counterfactual explanation translated into language guidance.

The key explanation step uses negative SHAP values to identify which feature changes would most effectively move a novice driver's corner behavior toward expert-level classification.

Those feature-level suggestions are then turned into natural-language coaching with a customized large language model, yielding feedback that is more interpretable than raw telemetry plots or scalar skill scores.

## Evaluation

The paper validates the system both algorithmically and in human-in-the-loop simulator experiments.

The reported result is not only that the classifier predicts skill level accurately, but that the generated feedback improves cornering and overall lap times. The paper also reports that participants retained some of the performance gains after the feedback was removed, which is a meaningful sign that the system taught something rather than only nudging behavior moment to moment.

## Notes / Critique

The strongest contribution is the combination of three things that are often separated: performance classification, counterfactual explanation, and language-based instruction.

Its main limitation for this vault is that the target is human training in simulation, not autonomous control on a physical racecar. Even so, it offers a useful window into how expert racing behavior might be decomposed, explained, and taught in a machine-readable way.

## Pages Created From This Source

- [[data_driven_driver_training_via_counterfactual_and_language_based_guidance_in_racing_scenarios]]
- [[racing_driver_training]]
