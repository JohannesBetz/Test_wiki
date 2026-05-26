---
tags: [paper]
date: 2026-05-26
task: robotics
venue: "arXiv 2025"
sources: 1
year: "2025"
doi: "10.48550/arXiv.2509.14353"
url: "https://doi.org/10.48550/arXiv.2509.14353"
topic:
  - embodied_autonomous_intelligence
  - real_world_robotic_reinforcement_learning
  - Highly_dynamic_autonomous_system
tech_backbone: [reinforcement_learning]
tech_representation: [sim_to_real_transfer]
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: [dreamcontrol]
hardware_used: [humanoids]
simulators_used: []
---

# DreamControl: Human-Inspired Whole-Body Humanoid Control for Scene Interaction via Guided Diffusion

> DreamControl: Human-Inspired Whole-Body Humanoid Control for Scene Interaction via Guided Diffusion | arXiv 2025 | Dvij Kalaria, Sudarshan S. Harithas, Pushkal Katara, Sangkyung Kwak, Sarthak Bhagat, Shankar Sastry, Srinath Sridhar, Sai Vemprala, Ashish Kapoor, and Jonathan Chung-Kuan Huang | DOI: 10.48550/arXiv.2509.14353

## Summary

This paper asks how a humanoid can achieve human-inspired whole-body control for interacting with scenes.

Its answer is [[dreamcontrol]], a guided-diffusion-based humanoid control system for scene interaction.

## Method

The central systems contribution is [[dreamcontrol]].

From the local metadata and public project record, the paper centers on:

- human-inspired whole-body humanoid control,
- scene interaction as the target regime,
- and guided diffusion as the central modeling ingredient.

For this vault, the important systems lesson is that natural humanoid scene interaction may be approached as a generative-control problem rather than only as a reactive controller or motion-tracking substrate.

## Key Results

The local metadata and project-page support place the paper in the real humanoid scene-interaction branch.

The most useful vault takeaway is broader than one benchmark:

**humanoid scene interaction is becoming a testbed not only for better controllers, but for richer generative priors over whole-body behavior.**

## Hardware Used

- [[humanoids]]

## Related Work

This paper belongs near [[physhsi_towards_a_real_world_generalizable_and_natural_humanoid_scene_interaction_system]], but it appears more explicitly generative-model-centric.

Compared with [[sonic_supersizing_motion_tracking_for_natural_humanoid_whole_body_control]], it is less about scaling motion tracking and more about guided generation of whole-body control behavior.

Compared with [[humanplus_humanoid_shadowing_and_imitation_from_humans]], it is less about data acquisition from humans and more about the control prior itself.

It also belongs near [[embodied_autonomous_intelligence]], because it explores whether richer internal generative structure can help produce more natural embodied interaction.

## Notes / Critique

The strongest contribution is the architectural direction. DreamControl gives the vault a concrete example of diffusion-style generative modeling entering humanoid whole-body control rather than remaining mostly in perception or offline synthesis.

The main caveat is that this ingest is anchored to strong local metadata and project-page support rather than a deep local full-text parse. So I’ve kept the note focused on the reliable systems framing rather than low-level algorithm details.
