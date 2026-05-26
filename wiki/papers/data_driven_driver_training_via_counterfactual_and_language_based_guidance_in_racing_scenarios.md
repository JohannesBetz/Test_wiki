---
tags: [paper]
date: 2026-05-13
task: autonomous_racing
venue: "IEEE Access 2025"
sources: 1
year: "2025"
doi: "10.1109/ACCESS.2025.3615128"
topic:
  - autonomous_racing
  - professional_race_driver_expertise
  - human_machine_interaction
  - autonomous_racing_simulation
tech_backbone: []
tech_representation: []
tech_generation: []
tech_conditioning: [text_conditioning]
tech_modality_alignment: []
tech_finetuning: []
tech_inference: [tool_use]
datasets_used: []
models_used: []
hardware_used: [cars_and_race_cars]
simulators_used: []
---

# Data-Driven Driver Training via Counterfactual and Language-Based Guidance in Racing Scenarios

> Data-Driven Driver Training via Counterfactual and Language-Based Guidance in Racing Scenarios | IEEE Access 2025 | Jonghak Bae, Hyeongwoo Nam, Kunhee Ryu, Jihye Lee, Jinsung Kim, Hokyun Chun, Jongtaek Han, and Jongeun Choi

## Summary

This paper asks how novice drivers in racing scenarios can be trained with personalized, interpretable, and scalable machine guidance rather than only one-on-one human coaching.

Its answer is an AI coaching framework that analyzes corner-specific performance, identifies what separates weaker and stronger driving behavior, and turns those differences into natural-language advice.

## Method

The system begins by clustering sequential driving behavior to generate pseudo skill labels in an unsupervised way.

Next, a classification model is trained on racing-critical corner features so that a driver's local performance level can be estimated from telemetry-derived behavior rather than from lap time alone.

The most distinctive technical contribution is the feedback mechanism:

- negative SHAP values are used to find which feature changes would most effectively push a novice corner toward expert-level classification,
- these counterfactual feature changes are then translated into natural-language coaching with a customized large language model.

That makes the framework a form of explainable, corner-specific virtual driver instruction rather than a generic coaching dashboard.

## Key Results

The paper reports both algorithmic validation and human-in-the-loop simulator experiments.

The key result is that the system improves cornering performance and total lap time, and that some of the gains persist after the feedback is removed. That retention result matters because it suggests the framework supports learning rather than only temporary compliance.

For this vault, another important result is methodological: the paper shows one way to convert expert-like racing behavior into actionable and interpretable training signals instead of opaque end scores.

## Hardware Used

- [[cars_and_race_cars]]


## Related Work

This paper belongs most directly near [[professional_race_driver_expertise]], because both are fundamentally about what expert driving looks like and how it can be communicated or transferred.

Compared with [[accelerating_autonomy_insights_from_pro_racers_in_the_era_of_autonomous_racing]], this paper is less about qualitative expert interviews and more about building a concrete machine coaching pipeline for novices.

It also connects to [[autonomous_racing_simulation]], because the human evaluation is carried out in a simulated racing environment, and to [[autonomous_vehicle_racing]] more broadly because it offers a human-training counterpart to machine-driving performance optimization.

## Notes / Critique

The strongest contribution is interpretability with actionability. Many driver-assistance or coaching systems can score behavior; fewer can explain how to improve in a corner-specific way that a human can immediately apply.

The main limitation is transfer scope. The paper validates the idea in simulation, so it remains open how well the same coaching logic survives real-world sensing noise, physical risk, and richer vehicle dynamics.
