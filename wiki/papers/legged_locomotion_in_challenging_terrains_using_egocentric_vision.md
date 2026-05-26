---
tags: [paper]
date: 2026-05-22
task: robotics
venue: "Conference on Robot Learning (CoRL) 2023"
sources: 1
year: "2023"
doi: ""
url: "https://proceedings.mlr.press/v205/agarwal23a.html"
topic:
  - Highly_dynamic_autonomous_system
  - high_speed_perception
  - real_world_robotic_reinforcement_learning
  - quadrupedal_locomotion
tech_backbone: [reinforcement_learning]
tech_representation: [perceptive_locomotion, sim_to_real_transfer]
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

# Legged Locomotion in Challenging Terrains using Egocentric Vision

> Legged Locomotion in Challenging Terrains using Egocentric Vision | Conference on Robot Learning (CoRL) 2023 | Ananye Agarwal, Ashish Kumar, Jitendra Malik, and Deepak Pathak | PMLR 205

## Summary

This paper asks whether a quadruped can use onboard egocentric vision to move robustly across challenging terrain without depending on privileged global terrain structure or heavy external perception machinery.

Its answer is yes: a learned locomotion policy can use egocentric vision to traverse varied rough terrain while remaining robust to disturbances and terrain uncertainty.

## Method

The training backbone is [[reinforcement_learning]].

The paper belongs in the [[perceptive_locomotion]] branch.

From the CoRL record and abstract support, the controller uses egocentric visual input as part of the control loop for terrain-aware locomotion, making perception directly relevant to action timing and body motion.

For this vault, the central systems lesson is that terrain-aware quadruped competence does not always need a heavy explicit mapping stack. In some settings, egocentric vision can provide enough grounded signal for a learned controller to act effectively.

## Key Results

The public record reports traversal over a large variety of terrains together with robustness to pushes, slippery surfaces, and rocky ground.

The most useful vault takeaway is broader than one terrain course:

**real-world legged competence can emerge from a compact vision-first policy when perception is tightly coupled to locomotion rather than treated as a separate module.**

## Hardware Used

- [[quadrupeds]]

## Related Work

This paper belongs near [[learning_robust_perceptive_locomotion_for_quadrupedal_robots_in_the_wild]], but it reads as a more compact egocentric-vision version of the perceptive-locomotion idea rather than a map-fusion-heavy one.

Compared with [[rma_rapid_motor_adaptation_for_legged_robots]], it puts more weight on visual terrain understanding and less on latent dynamics inference from recent history.

Compared with [[agile_but_safe_learning_collision_free_high_speed_legged_locomotion]], it is less about explicit safety switching and more about direct visual terrain competence under challenging surfaces.

It also belongs near [[high_speed_perception]], because it shows that fast perception in legged robotics can be embodied and local rather than only long-range and map-centric.

## Notes / Critique

The strongest contribution is the demonstration that egocentric vision can be enough for meaningful terrain-aware locomotion on a small quadruped. That is a nice counterweight to the vault’s more map-heavy or optimizer-heavy terrain-control papers.

The main caveat is that the current ingest is anchored to the CoRL proceedings record and public abstract support rather than a clean full-text parse of the local PDF, so I’ve kept the note at the level of reliable systems interpretation rather than speculative implementation detail.
