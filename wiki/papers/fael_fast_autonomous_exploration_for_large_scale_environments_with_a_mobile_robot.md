---
tags: [paper]
date: 2026-05-20
task: mobile_robot_navigation
venue: "IEEE Robotics and Automation Letters"
sources: 1
year: "2023"
doi: "10.1109/LRA.2023.3236573"
topic:
  - cognitive_navigation
  - embodied_autonomous_intelligence
tech_backbone: []
tech_representation: [fast_autonomous_exploration]
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: [fael]
hardware_used: [mobile_robots]
simulators_used: []
---

# FAEL: Fast Autonomous Exploration for Large-Scale Environments with a Mobile Robot

> FAEL: Fast Autonomous Exploration for Large-Scale Environments with a Mobile Robot | IEEE Robotics and Automation Letters, 2023 | Junlong Huang, Boyu Zhou, Zhengping Fan, Yilin Zhu, Yingrui Jie, Longwei Li, and Hui Cheng | DOI: 10.1109/LRA.2023.3236573

## Summary

This paper appears to tackle a classic but still important autonomy problem: how can a mobile robot explore large environments quickly and effectively without relying on a human operator or a narrow local heuristic?

Its answer is `FAEL`, a fast autonomous exploration method aimed at large-scale settings.

## Method

The paper's central idea is captured here as [[fast_autonomous_exploration]].

At a high level, the contribution appears to be a systems-oriented exploration strategy for mobile robots that is designed to preserve speed and autonomy quality as the environment grows larger.

That makes it a natural neighbor to:

- [[cognitive_navigation]], where exploration is part of a perception-decision-execution loop,
- [[a_survey_on_learning_motion_planning_and_control_for_mobile_robots_toward_embodied_intelligence]], which frames mobile-robot motion generation more broadly,
- and the vault's broader embodied-autonomy branch, where open-ended interaction with the environment matters as much as reaching one fixed goal.

## Key Result

At the vault level, the key result is conceptual:

**efficient autonomy in large environments is not only a mapping problem or only a planning problem, but a navigation-loop design problem where exploration quality has to scale with the environment.**

That gives the wiki a useful counterpoint to the racing papers: here the hard problem is not near-limit control, but efficient open-ended discovery and coverage.

## Hardware Used

- [[mobile_robots]]


## Related Work

Compared with the racing-focused papers in the vault, this one is much less about dynamic-envelope exploitation and much more about mission-level autonomy in unknown large spaces.

Compared with the broader [[cognitive_navigation_review]], it likely provides a more concrete mobile-robot exploration instantiation of the perception-decision-execution framing.

Compared with the learning-based mobile-robot survey, it adds a specific practical exploration method rather than a synthesis view.

## Notes / Critique

The strongest value of this paper for the vault is diversity of autonomy workload. It strengthens the navigation branch by adding a large-scale exploration problem, which is a very different stress test from racing yet still deeply relevant to embodied autonomy.

The main caveat of this ingest is practical: while the metadata was rich, I did not have a clean full-text extraction path in this workspace, so this note is intentionally careful and should be deepened later if fuller text access becomes available.
