---
tags: [paper]
date: 2026-05-26
task: robotics
venue: "IEEE Robotics and Automation Letters"
sources: 1
year: "2023"
doi: "10.1109/LRA.2023.3290509"
url: "https://doi.org/10.1109/LRA.2023.3290509"
topic:
  - Highly_dynamic_autonomous_system
  - quadrupedal_locomotion
tech_backbone: [reinforcement_learning]
tech_representation: [adversarial_motion_priors]
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

# Learning Robust and Agile Legged Locomotion Using Adversarial Motion Priors

> Learning Robust and Agile Legged Locomotion Using Adversarial Motion Priors | IEEE Robotics and Automation Letters 2023 | Jinze Wu, Guiyang Xin, Chenkun Qi, and Yufei Xue | DOI: 10.1109/LRA.2023.3290509

## Summary

This paper asks how a legged robot can learn locomotion that is not only reward-maximizing, but also robust, agile, and motion-structured in a more natural way than sparse task rewards usually encourage by themselves.

Its answer is to use [[adversarial_motion_priors]] as an additional learning signal inside the locomotion-training pipeline.

## Method

The training backbone is [[reinforcement_learning]].

The central idea is [[adversarial_motion_priors]].

At a high level, the method augments locomotion learning with an adversarial prior over motion behavior, so the policy is optimized not only for task reward but also for whether its movement matches a learned notion of desirable motion structure.

For this vault, the important systems lesson is that legged agility may sometimes depend less on inventing better reward terms and more on constraining the policy toward better motion manifolds during learning.

## Key Results

The public record supports the main claim that adversarial motion priors improve the robustness and agility of learned legged locomotion.

The most useful vault takeaway is broader than one benchmark:

**legged locomotion quality can be shaped through learned motion priors, not only through explicit controller structure or reward shaping.**

## Hardware Used

- [[quadrupeds]]

## Related Work

This paper belongs near [[rapid_locomotion_via_reinforcement_learning]], but it uses a different lever. Rapid locomotion leans heavily on curriculum and sim-to-real discipline, while this paper leans on a stronger learned prior over what locomotion should look like.

Compared with [[rma_rapid_motor_adaptation_for_legged_robots]], it is less about inferring hidden external conditions online and more about structuring the locomotion policy itself during training.

Compared with [[perceptive_locomotion_through_nonlinear_model_predictive_control]], it is much more learning-centric and much less explicit about terrain or control structure.

It also belongs near [[Highly_dynamic_autonomous_system]], because one recurring issue in high-dynamic robotics is that purely task-driven objectives can produce brittle or ugly behaviors unless the learning system is given richer structural guidance.

## Notes / Critique

The strongest contribution is conceptual: it treats `good motion` as something that can be learned as a prior instead of fully handwritten into the objective.

The main caveat is that the current ingest is anchored to the RA-L record, DOI metadata, and indirect citation context rather than a clean full-text parse of the local PDF. So I’ve kept this note at the level of reliable architectural interpretation rather than pretending we have every experimental detail pinned down.
