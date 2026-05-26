---
tags: [paper]
date: 2026-05-26
task: robotics
venue: "Proceedings of The 8th Conference on Robot Learning (CoRL 2024 / PMLR 270)"
sources: 1
year: "2025"
doi: ""
url: "https://proceedings.mlr.press/v270/yu25b.html"
topic:
  - Highly_dynamic_autonomous_system
  - high_speed_perception
  - real_world_robotic_reinforcement_learning
  - quadrupedal_locomotion
tech_backbone: [reinforcement_learning]
tech_representation: [sim_to_real_transfer]
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: [lucidsim]
hardware_used: [quadrupeds]
simulators_used: []
---

# Learning Visual Parkour from Generated Images

> Learning Visual Parkour from Generated Images | Proceedings of The 8th Conference on Robot Learning (CoRL 2024 / PMLR 270) | Alan Yu, Ge Yang, Ran Choi, Yajvan Ravan, John Leonard, and Phillip Isola | PMLR 270

## Summary

This paper asks how a quadruped can learn visual parkour from RGB-only observations when realistic visual simulation is usually the weakest part of the sim-to-real pipeline.

Its answer is to train the policy using generated egocentric image sequences through [[lucidsim]], then transfer zero-shot to the real robot.

## Method

The training backbone is [[reinforcement_learning]].

The central systems idea is [[lucidsim]].

From the CoRL record and abstract support, the method synthesizes diverse and physically accurate image sequences from the robot's egocentric perspective, then uses those for visual parkour training in simulation.

For this vault, the important systems lesson is that visual sim-to-real transfer can be improved not only through better policy design, but through better generation of the visual world the policy trains in.

## Key Results

The public record reports zero-shot transfer to a real quadruped using only RGB observations from a low-cost off-the-shelf camera.

The most useful vault takeaway is broader than one obstacle course:

**generated visual environments can become a core ingredient of high-dynamic robot learning when real-image collection is too narrow and conventional simulation is too visually thin.**

## Hardware Used

- [[quadrupeds]]

## Related Work

This paper belongs near [[sim_to_real_transfer]], but it pushes that branch in a more visual and generative direction than the existing quadruped transfer papers.

Compared with [[legged_locomotion_in_challenging_terrains_using_egocentric_vision]], it is more focused on how the visual training world is synthesized than on the compactness of the deployed visual policy itself.

Compared with [[robot_parkour_learning]], it is less about unifying many obstacle skills under one policy and more about how to make RGB-only parkour learning transfer from simulation to reality.

It also belongs near [[high_speed_perception]], because the real issue is not only locomotion but whether a robot can trust RGB-only perception under aggressive obstacle-rich motion.

## Notes / Critique

The strongest contribution is that it treats the image-generation pipeline itself as part of the robotics method. That gives the vault a much cleaner example of `generative models as sim-to-real infrastructure` rather than only as generic foundation-model hype.

The main caveat is that the current ingest is anchored to the CoRL proceedings record, project-page summary, and public abstract support rather than a clean full-text parse of the local PDF, so I’ve kept the note at the level of reliable systems interpretation.
