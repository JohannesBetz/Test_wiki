---
tags: [paper]
date: 2026-05-26
task: robotics
venue: "2021 IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS)"
sources: 1
year: "2021"
doi: "10.1109/IROS51168.2021.9635838"
url: "https://doi.org/10.1109/IROS51168.2021.9635838"
topic:
  - Highly_dynamic_autonomous_system
  - quadrupedal_locomotion
tech_backbone: []
tech_representation: [motion_matching]
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
hardware_used: [quadrupeds]
simulators_used: []
---

# Animal Gaits on Quadrupedal Robots Using Motion Matching and Model-Based Control

> Animal Gaits on Quadrupedal Robots Using Motion Matching and Model-Based Control | 2021 IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS) | Dongho Kang, Simon Zimmermann, and Stelian Coros | DOI: 10.1109/IROS51168.2021.9635838

## Summary

This paper asks how quadruped robots can move in a way that is not only dynamically stable, but also more animal-like in gait structure and overall body motion.

Its answer is a control pipeline that combines [[motion_matching]] with model-based control.

## Method

The central idea is [[motion_matching]].

From the IROS record and abstract support, the system uses motion matching and inertialization to retrieve and transition among animal-inspired gait fragments, then converts those into reference trajectories that are tracked by a model-based quadruped controller.

For this vault, the important systems lesson is that gait diversity and naturalness can be introduced as a retrieval-and-tracking problem rather than only as a policy-learning problem.

## Key Results

The public record reports simulation results across multiple quadruped robot models.

The main high-level result is that the system can reproduce several animal-like motion characteristics, including speed-specific gaits, nonperiodic footfall patterns, and natural variation in body movement.

The most useful vault takeaway is broader than one simulated gait:

**quadruped agility and naturalness can be improved through motion-library selection coupled to model-based tracking, not only through end-to-end learning or one fixed control law.**

## Hardware Used

- [[quadrupeds]]

## Related Work

This paper belongs near [[motion_matching]], where it acts as the quadruped-side anchor for the technique.

Compared with [[perceptive_humanoid_parkour_chaining_dynamic_human_skills_via_motion_matching]], it uses motion matching for smoother animal-like gait selection rather than for aggressive perceptive parkour skill chaining.

Compared with [[highly_dynamic_quadruped_locomotion_via_whole_body_impulse_control_and_model_predictive_control]], it is less about optimizing one dynamic controller and more about enriching the reference-motion structure that the controller tracks.

It also belongs near [[quadrupedal_locomotion]], because it widens the branch from speed and robustness toward natural gait diversity and footfall variability.

## Notes / Critique

The strongest contribution is the bridge between data-driven animation methods and robotics control. It makes the quadruped branch feel less split between `pure control` and `pure learning`.

The main caveat is that the validation described in the public record is simulation-focused. So I’ve treated this as an important architectural reference rather than as evidence of the same real-world maturity as the strongest hardware-deployed quadruped papers.
