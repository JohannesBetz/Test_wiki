---
tags: [paper]
date: 2026-05-13
task: ai_systems
venue: "International Journal of Robotics Research 2025"
sources: 1
year: "2025"
doi: "10.1177/02783649241281508"
url: "https://doi.org/10.1177/02783649241281508"
topic:
  - foundation_models_for_intelligent_decision_making
  - embodied_autonomous_intelligence
  - real_world_robotic_foundation_models
tech_backbone: []
tech_representation: []
tech_generation: [foundation_models_for_intelligent_decision_making]
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
hardware_used: [multiple_robot_embodiments]
simulators_used: []
---

# Foundation models in robotics: Applications, challenges, and the future

> Foundation models in robotics: Applications, challenges, and the future | International Journal of Robotics Research 2025 | Roya Firoozi, Johnathan Tucker, Stephen Tian, Anirudha Majumdar, Jiankai Sun, Weiyu Liu, Yuke Zhu, Shuran Song, Ashish Kapoor, Karol Hausman, Brian Ichter, Danny Driess, Jiajun Wu, Cewu Lu, and Mac Schwager

## Summary

This paper surveys how pretrained foundation models are being used across robotics and what they may change in robot autonomy.

Its core value for this vault is that it gives a broad robotics-centered view of the field: not just that foundation models are promising, but where they are being inserted into robot systems, what they seem to improve, and why their deployment remains difficult.

## Method

The paper is an application-oriented survey of foundation models in robotics.

It reviews how pretrained models can contribute to multiple parts of the autonomy stack, from perception and scene understanding to reasoning, planning, and action-related components. At the same time, it emphasizes the mismatch between internet-scale pretraining and the requirements of embodied systems.

That makes the paper a useful interpretive layer for the vault. It helps explain how large models are being integrated into robotics without assuming that one monolithic model simply replaces the rest of the stack.

## Key Results

For this vault, the key result is the overall framing: foundation models may improve generalization and flexibility in robotics, but their usefulness is strongly shaped by system integration, robotic data quality, safety, and real-time execution constraints.

The paper therefore argues neither for blind optimism nor for dismissal. It presents foundation models as meaningful building blocks for robotics, but only within architectures that respect embodiment and task demands.

## Hardware Used

- [[multiple_robot_embodiments]]


## Related Work

This paper belongs directly near [[foundation_models_for_intelligent_decision_making]] and [[real_world_robotic_foundation_models]].

Compared with [[real_world_robot_applications_of_foundation_models_a_review]], it is broader and more applications-focused, while the Kawaharazuka review is more explicitly filtered through physical deployment reality.

Compared with [[towards_general_purpose_robots_via_foundation_models_a_survey_and_meta_analysis]], this paper is less about the grand question of robotic generality and more about the practical field landscape of current applications, challenges, and trajectories.

It also complements [[racevla_vla_based_racing_drone_navigation_with_human_like_behaviour]] by giving a larger context for why VLA and multimodal-action systems are seen as important, even when their embodied deployment is still fragile.

## Notes / Critique

The strongest contribution is balance. The paper is broad enough to map the robotics-foundation-model field, but practical enough to keep the discussion connected to autonomy-stack design instead of drifting into abstract capability talk.

For this vault, it is a valuable anchor because it strengthens the robotics branch without forcing every foundation-model paper to carry the whole framing burden by itself.
