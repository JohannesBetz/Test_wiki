---
tags: [model]
date: 2026-05-08
sources: 1
---

# RaceVLA

## Definition

RaceVLA is the racing-drone system introduced in [[racevla_vla_based_racing_drone_navigation_with_human_like_behaviour]]. It adapts the vision-language-action paradigm to FPV aerial navigation with language-conditioned low-level control.

## Key Approaches

- Fine-tuned OpenVLA-style backbone specialized for racing-drone behavior.
- FPV visual input paired with natural-language prompts.
- Direct prediction of translational velocity and yaw-rate control actions.
- LoRA-style adaptation on a racing-drone dataset.
- Real-drone deployment with custom racing hardware and external inference support.

## Representative Papers

- [[racevla_vla_based_racing_drone_navigation_with_human_like_behaviour]]

## Open Problems

RaceVLA is an early multimodal-control result rather than a mature racing platform. Future work would need faster inference, stronger onboard autonomy, higher-speed operation, and much clearer robustness under appearance, dynamics, and language-prompt variation.
