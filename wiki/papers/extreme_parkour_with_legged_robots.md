---
tags: [paper]
date: 2026-05-26
task: robotics
venue: "arXiv 2023"
sources: 1
year: "2023"
doi: "10.48550/arXiv.2309.14341"
url: "https://doi.org/10.48550/arXiv.2309.14341"
topic:
  - Highly_dynamic_autonomous_system
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

# Extreme Parkour with Legged Robots

> Extreme Parkour with Legged Robots | arXiv 2023 | Xuxin Cheng, Kexin Shi, Ananye Agarwal, and Deepak Pathak | DOI: 10.48550/arXiv.2309.14341

## Summary

This paper asks whether a small low-cost quadruped with imprecise actuation and noisy depth sensing can still achieve genuinely extreme parkour behavior.

Its answer is yes: a single end-to-end neural policy can produce highly precise agile behavior directly from depth input.

## Method

The training backbone is [[reinforcement_learning]].

From the public abstract and project-page record, the system:

- uses a single neural network policy operating directly on depth images,
- is trained in simulation with large-scale RL,
- and targets direct end-to-end control under imprecise sensing and actuation.

For this vault, the important systems lesson is that extreme agility can emerge even when the embodiment is cheap and noisy, provided the learning stack is strong enough to compensate.

## Key Results

The public record reports high jumps over obstacles about twice the robot's height, long jumps across gaps about twice its body length, handstands, tilted-ramp running, and generalization to novel obstacle courses with different physical properties.

The most useful vault takeaway is broader than one stunt:

**extreme quadruped parkour can be framed as a learned end-to-end capability on low-cost hardware rather than only as a premium-hardware showcase.**

## Hardware Used

- [[quadrupeds]]

## Related Work

This paper belongs near [[robot_parkour_learning]], but it appears more directly focused on `extreme` maneuvers under inexpensive and noisy hardware assumptions than on broad parkour repertoire organization.

Compared with [[pie_parkour_with_implicit_explicit_learning_framework_for_legged_robots]], it appears more purely end-to-end and less centered on preserving an explicit estimation layer.

Compared with [[learning_visual_parkour_from_generated_images]], it is less about image-generation-assisted transfer and more about what can already be extracted from a rough real sensing stack through RL.

It also belongs near [[perceptive_locomotion]], because the depth image is directly control-relevant rather than a passive perception artifact.

## Notes / Critique

The strongest contribution is the claim about hardware tolerance. This paper suggests that one route to extreme autonomy is not just better sensors and tighter mechanics, but learning policies that can survive poor sensing and imperfect embodiment.

The main caveat is that this ingest is anchored to the public abstract/project record and a weak local PDF text layer rather than a rich local full-text parse. So I’ve kept the note focused on the reliable high-level picture.
