---
tags: [source]
date: 2026-05-08
sources: 1
---

# Serpiva RaceVLA Source

> Source: `raw/pdfs/Seripva_RaceVLA.pdf`
> Paper: RaceVLA: VLA-based Racing Drone Navigation with Human-like Behaviour, arXiv 2025

## Summary

This paper introduces RaceVLA, a vision-language-action (`VLA`) system for autonomous racing drones. Instead of separating perception, planning, and control into a classical stack, the model maps first-person video and language instructions toward direct control actions.

For this vault, the paper matters because it brings foundation-model-style multimodal control into autonomous drone racing, which is a noticeably different direction from the RL-heavy Swift line.

## Method

The system fine-tunes an OpenVLA-style backbone on a racing-drone dataset built around FPV observations and command-conditioned flight behavior.

The resulting policy consumes:

- first-person video,
- natural-language task prompts,
- and recent control context,

and predicts low-level action outputs for drone motion, including translational velocity commands and yaw-rate control.

The paper positions RaceVLA against OpenVLA and RT-2, adapting the broader VLA idea to a high-speed aerial setting with tight latency and dynamics constraints.

## Evaluation

The authors report real-drone experiments with a custom 8-inch racing platform using onboard sensing and server-side VLA inference. The paper emphasizes both benchmark-style generalization axes and practical flight capability.

Its key claim is that a racing-specific VLA can outperform broader pretrained baselines in this domain, especially on motion and semantic generalization, while remaining competitive on visual and physical generalization.

## Notes / Critique

The interesting part is not only that it uses a foundation-model-style architecture, but that it tries to push that style into a domain where control is fast, embodied, and unforgiving. That makes it a useful bridge between [[foundation_models_for_intelligent_decision_making]] and [[autonomous_drone_racing]].

The obvious caution is systems realism: server-side inference at low update rate is a long way from the tight onboard latency budgets of the strongest racing systems. So the paper is best read as an early proof of direction, not yet a replacement for stronger dedicated control stacks.

## Pages Created From This Source

- [[racevla_vla_based_racing_drone_navigation_with_human_like_behaviour]]
- [[racevla]]
- [[vision_language_action_models]]
