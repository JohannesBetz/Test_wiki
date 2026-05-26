---
tags: [paper]
date: 2026-05-26
task: robotics
venue: "Proceedings of The 9th Conference on Robot Learning (CoRL 2025 / PMLR 305)"
sources: 1
year: "2025"
doi: ""
url: "https://proceedings.mlr.press/v305/zhang25b.html"
topic:
  - Highly_dynamic_autonomous_system
  - embodied_autonomous_intelligence
  - real_world_robotic_reinforcement_learning
tech_backbone: [reinforcement_learning]
tech_representation: [sim_to_real_transfer]
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: [hub]
hardware_used: [humanoids]
simulators_used: []
---

# HuB: Learning Extreme Humanoid Balance

> HuB: Learning Extreme Humanoid Balance | Proceedings of The 9th Conference on Robot Learning (CoRL 2025 / PMLR 305) | Tong Zhang, Boyuan Zheng, Ruiqian Nai, Yingdong Hu, Yen-Jen Wang, Geng Chen, Fanqi Lin, Jiongye Li, Chuye Hong, Koushil Sreenath, and Yang Gao | PMLR 305

## Summary

This paper asks how a humanoid can learn extreme balance skills that go beyond ordinary locomotion, including stable single-leg poses and high-kick configurations that are highly sensitive to reference errors and disturbance.

Its answer is [[hub]], a unified framework for extreme humanoid balance.

## Method

The training backbone is [[reinforcement_learning]].

The central systems contribution is [[hub]].

From the CoRL record and abstract support, HuB integrates:

- reference motion refinement,
- balance-aware policy learning,
- and sim-to-real robustness training.

For this vault, the important systems lesson is that balance-intensive humanoid skills are difficult not because they require more of the same locomotion pipeline, but because they amplify reference-quality, morphology-mismatch, and robustness problems that ordinary walking can sometimes hide.

## Key Results

The public record reports real-world validation on the Unitree G1 humanoid across extreme quasi-static balance tasks such as Swallow Balance and Bruce Lee's Kick, with robustness to strong external disturbances.

The most useful vault takeaway is broader than one benchmark:

**humanoid balance can be treated as a first-class learned capability with its own transfer and robustness challenges, not only as a byproduct of locomotion training.**

## Hardware Used

- [[humanoids]]

## Related Work

This paper belongs near [[real_world_humanoid_locomotion_with_reinforcement_learning]], but it shifts the target from locomotion competence to balance-intensive whole-body skill.

Compared with [[humanoid_parkour_learning]], it is less about traversing diverse obstacles and more about maintaining extreme postural stability under disturbance.

Compared with [[hiking_in_the_wild_a_scalable_perceptive_parkour_framework_for_humanoids]], it appears less perception-centric and more balance- and motion-reference-centric.

It also belongs near [[Highly_dynamic_autonomous_system]], because some of the hardest high-dynamic questions are not only about speed, but about how little stability margin a system can tolerate while still remaining controllable.

## Notes / Critique

The strongest contribution is the choice of target behavior. Extreme balance is a very clean stress test for whether a humanoid control stack really understands whole-body stability rather than only gait repetition.

The main caveat is that the current ingest is anchored to the CoRL proceedings record and project-page abstract support rather than a clean full-text parse of the local PDF. So I’ve kept the note at the level of reliable systems interpretation rather than overclaiming implementation details.
