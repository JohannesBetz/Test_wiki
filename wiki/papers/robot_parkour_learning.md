---
tags: [paper]
date: 2026-05-22
task: robotics
venue: "Conference on Robot Learning (CoRL) 2023"
sources: 1
year: "2023"
doi: "10.48550/arXiv.2309.05665"
url: "https://proceedings.mlr.press/v229/zhuang23a.html"
topic:
  - Highly_dynamic_autonomous_system
  - real_world_robotic_reinforcement_learning
  - quadrupedal_locomotion
tech_backbone: [reinforcement_learning]
tech_representation: [perceptive_locomotion]
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

# Robot Parkour Learning

> Robot Parkour Learning | Conference on Robot Learning (CoRL) 2023 | Ziwen Zhuang, Zipeng Fu, Jianren Wang, Christopher G. Atkeson, Sören Schwertfeger, Chelsea Finn, and Hang Zhao | DOI: 10.48550/arXiv.2309.05665

## Summary

This paper asks whether a quadrupedal robot can learn one vision-based parkour policy that covers a diverse set of agile obstacle-crossing behaviors in the real world.

Its answer is yes: a single end-to-end policy can support climbing, leaping, crawling, squeezing, and running across challenging environments.

## Method

The paper uses [[reinforcement_learning]] to generate diverse parkour skills and then distills them into one end-to-end vision-based deployment policy.

From the public abstract, the training is inspired by direct collocation, which helps shape the skill-learning process without relying on reference motion data.

For this vault, the important point is that the result sits between locomotion and navigation: the policy has to perceive the environment, decide which maneuver applies, and execute the maneuver within one learned parkour stack.

## Key Results

According to the public abstract and project page, the learned system transfers to low-cost quadrupedal robots using egocentric depth sensing and can autonomously select appropriate parkour behaviors in challenging real-world environments.

The most useful vault takeaway is broader than one specific obstacle:

**quadruped agility can be organized as a unified perceptive parkour problem rather than only as isolated terrain skills.**

## Hardware Used

- [[quadrupeds]]

## Related Work

This paper belongs directly near [[quadrupedal_locomotion]], where it extends the legged branch from fast locomotion into multi-skill obstacle traversal.

Compared with [[learning_robust_perceptive_locomotion_for_quadrupedal_robots_in_the_wild]], this paper puts more emphasis on skill diversity and obstacle-specific maneuvering than on robust terrain perception alone.

Compared with [[perceptive_locomotion_through_nonlinear_model_predictive_control]], it represents the learning-heavy parkour alternative to structured predictive control.

It also belongs near [[humanoid_parkour_learning]], where it can be read as the quadruped precursor to the later humanoid whole-body parkour formulation.

## Notes / Critique

The strongest contribution is the diversity of behaviors under one policy. It makes parkour look like a coherent learned capability rather than a pile of narrow demos.

The main caveat is still generalization pressure: once one policy has to span many maneuvers, the key question becomes whether the skill repertoire is genuinely unified or just broad enough for the tested obstacle family.
