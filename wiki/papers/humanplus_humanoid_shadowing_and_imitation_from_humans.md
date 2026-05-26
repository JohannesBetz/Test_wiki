---
tags: [paper]
date: 2026-05-26
task: robotics
venue: "Proceedings of The 8th Conference on Robot Learning (CoRL 2024 / PMLR 270)"
sources: 1
year: "2025"
doi: "10.48550/arXiv.2406.10454"
url: "https://proceedings.mlr.press/v270/fu25a.html"
topic:
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
models_used: [humanplus]
hardware_used: [humanoids]
simulators_used: []
---

# HumanPlus: Humanoid Shadowing and Imitation from Humans

> HumanPlus: Humanoid Shadowing and Imitation from Humans | Proceedings of The 8th Conference on Robot Learning (CoRL 2024 / PMLR 270) | Zipeng Fu, Qingqing Zhao, Qi Wu, Gordon Wetzstein, and Chelsea Finn | DOI: 10.48550/arXiv.2406.10454

## Summary

This paper asks how humanoid robots can learn whole-body motion and useful autonomous skills directly from human data.

Its answer is [[humanplus]], a full-stack humanoid shadowing and imitation system.

## Method

The training backbone combines [[reinforcement_learning]] and supervised behavior cloning.

The central systems contribution is [[humanplus]].

From the public abstract and project-page record, the system:

- trains a low-level policy in simulation from roughly 40 hours of human motion data,
- transfers that policy to real-world humanoid shadowing from a single RGB camera,
- uses shadowing for whole-body teleoperation data collection,
- and then trains skill policies from egocentric-vision demonstrations.

For this vault, the important systems lesson is that humanoid learning from human data may require a complete data-collection-and-imitation pipeline, not only a stronger controller.

## Key Results

The public record reports real-time human body and hand shadowing and autonomous task completion on a customized 33-DoF 180 cm humanoid across tasks such as standing up after wearing a shoe, unloading warehouse racks, folding a sweatshirt, rearranging objects, typing, and greeting another robot.

The most useful vault takeaway is broader than any one task:

**humanoid autonomy may scale faster when human motion, humanoid teleoperation, and autonomous imitation learning are linked into one continuous full-stack pipeline.**

## Hardware Used

- [[humanoids]]

## Related Work

This paper belongs near [[real_world_humanoid_locomotion_with_reinforcement_learning]], but it shifts the emphasis from locomotion competence to human-data-driven whole-body skill acquisition.

Compared with [[physhsi_towards_a_real_world_generalizable_and_natural_humanoid_scene_interaction_system]], it appears less scene-interaction-centric and more focused on how to acquire humanoid skill data from humans.

Compared with [[sonic_supersizing_motion_tracking_for_natural_humanoid_whole_body_control]], it appears less about enlarging the motion-tracking substrate itself and more about building a shadowing-to-imitation pipeline.

It also belongs near [[embodied_autonomous_intelligence]], because it operationalizes a strong version of the embodiment argument: humanoids can leverage human data precisely because their morphology makes that transfer meaningful.

## Notes / Critique

The strongest contribution is the systems pipeline from human motion to autonomous humanoid skill. This makes HumanPlus an especially useful reference for the vault’s broader `experience` and `human data` discussions.

The main caveat is that this ingest is anchored to a clean public abstract/project record and weak local PDF text layer rather than a deep local full-text parse. So I’ve kept the note focused on the reliable pipeline picture.
