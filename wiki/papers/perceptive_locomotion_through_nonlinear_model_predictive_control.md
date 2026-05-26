---
tags: [paper]
date: 2026-05-22
task: robotics
venue: "IEEE Transactions on Robotics"
sources: 1
year: "2023"
doi: "10.1109/TRO.2023.3275384"
url: "https://doi.org/10.1109/TRO.2023.3275384"
topic:
  - Highly_dynamic_autonomous_system
  - high_speed_perception
  - quadrupedal_locomotion
tech_backbone: [model_predictive_control]
tech_representation: [perceptive_locomotion, perceptive_nonlinear_model_predictive_control]
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

# Perceptive Locomotion Through Nonlinear Model-Predictive Control

> Perceptive Locomotion Through Nonlinear Model-Predictive Control | IEEE Transactions on Robotics 39(5), 2023 | Ruben Grandia, Fabian Jenelten, Shaohui Yang, Farbod Farshidian, and Marco Hutter | DOI: 10.1109/TRO.2023.3275384

## Summary

This paper asks whether a quadruped can perform dynamic locomotion over difficult terrain while keeping perception, foothold feasibility, and full-body motion generation inside one real-time optimization loop.

Its answer is yes: exteroceptive terrain information can be converted into locally tractable terrain constraints and embedded directly into an online nonlinear MPC controller.

## Method

The central idea is [[perceptive_nonlinear_model_predictive_control]].

The pipeline builds a robot-centric terrain representation and extracts computationally cheaper local structure from it, including steppability classification, plane segmentation, and a signed distance field.

Those terrain abstractions are then used to formulate local convex inequality constraints inside an online [[model_predictive_control]] problem. The optimizer jointly reasons about footholds, full-body motion, collision avoidance, and the underactuated dynamics of the quadruped in real time.

For this vault, the important systems lesson is that perception does not merely guide a heuristic foothold selector. It directly reshapes the optimization problem that generates motion.

## Key Results

The paper reports dynamic locomotion on challenging terrain such as gaps, slopes, and stepping stones, with validation in simulation and on physical ANYmal hardware.

The most useful vault takeaway is broader than the specific benchmark tasks:

**perceptive locomotion can be realized as structured predictive control, not only as learned policy fusion.**

## Hardware Used

- [[quadrupeds]]

## Related Work

This paper belongs directly near [[quadrupedal_locomotion]], where it adds a model-based perceptive-control complement to the current legged-robotics branch.

Compared with [[learning_robust_perceptive_locomotion_for_quadrupedal_robots_in_the_wild]], this paper is less about teacher-student policy learning and more about embedding terrain understanding directly into a full online optimizer.

Compared with [[highly_dynamic_quadruped_locomotion_via_whole_body_impulse_control_and_model_predictive_control]], it keeps the predictive-control spine but makes terrain perception much more central to what the optimizer can plan.

It also belongs near [[high_speed_perception]], because it shows that at high speed perception can matter not just for recognizing the world, but for changing the feasible set of the control problem itself.

## Notes / Critique

The strongest contribution is architectural clarity. The paper turns messy terrain into optimization-compatible constraints without abandoning the discipline of online nonlinear MPC.

The main caveat is computational and representation dependence. The whole story works only if the local terrain abstractions remain informative enough and cheap enough for real-time use; otherwise the controller either becomes too slow or too optimistic about terrain geometry.
