---
tags: [paper]
date: 2026-05-22
task: robotics
venue: "arXiv"
sources: 1
year: "2025"
doi: "10.48550/arXiv.2506.02835"
url: "https://doi.org/10.48550/arXiv.2506.02835"
topic:
  - Highly_dynamic_autonomous_system
  - embodied_autonomous_intelligence
  - quadrupedal_locomotion
tech_backbone: []
tech_representation: []
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

# High-speed control and navigation for quadrupedal robots on complex and discrete terrain

> High-speed control and navigation for quadrupedal robots on complex and discrete terrain | arXiv 2025 | Hyeongjun Kim, Hyunsik Oh, Jeongsoo Park, Yunho Kim, Donghoon Youm, Moonkyu Jung, Minho Lee, and Jemin Hwangbo | DOI: 10.48550/arXiv.2506.02835

## Summary

This paper asks how a legged robot can stay fast and purposeful when the terrain is not smooth, continuous, or easy to model.

That question makes it a strong adjacent paper for this vault. In racecars and drones, the hard part is often operating near the dynamic limit. In quadrupeds on complex and discrete terrain, the same pressure appears in a different body form: the robot must move quickly while keeping navigation, foothold selection, and whole-body stability aligned.

## Method

From the recoverable metadata, the most important structural claim is already visible in the title:

**control and navigation are treated as one coupled problem.**

That matters because difficult terrain breaks the fantasy that a robot can plan a route at one layer and simply execute it below. On complex and discrete terrain, locomotion feasibility shapes navigation choices directly, and navigation mistakes immediately become control failures.

So the paper belongs in the same design family as other vault entries that tightly couple environment understanding with fast control under hard physical constraints.

## Key Result

The vault-level result is not a racing benchmark, but a broader extension of the extreme-autonomy thesis:

**superior high-speed embodied autonomy is not limited to wheeled or aerial systems; it also depends on whether legged robots can navigate and control themselves quickly on harsh terrain without collapsing into overly cautious motion.**

That makes the paper useful as evidence that the high-dynamics problem generalizes across embodiments.

## Hardware Used

- [[quadrupeds]]


## Related Work

This paper belongs naturally near [[Highly_dynamic_autonomous_system]], where the common issue is not the specific platform but the need to act quickly under nonlinear dynamics, narrow safety margins, and rapidly changing feasibility.

It also pairs well with [[high_speed_accurate_robot_control_using_learned_forward_kinodynamics_and_non_linear_least_squares_optimization]], which studies high-speed control for small mobile robots when simplified models stop being accurate enough. The embodiment changes, but the deeper theme is the same: high-speed autonomy needs control-relevant models and execution loops that remain valid once the physics gets unforgiving.

Compared with [[learning_vision_based_pursuit_evasion_robot_policies]], this paper is less about adversarial interaction and more about terrain-conditioned locomotion and navigation. But both show that quadrupeds can now act as serious embodied-autonomy platforms rather than only as toy examples of locomotion.

It also reinforces a point already made in [[deep_reinforcement_learning_for_robotics_a_survey_of_real_world_successes]]: quadruped locomotion is one of the domains where real-world embodied competence appears much more mature than in many other robotics settings.

## Notes / Critique

The strongest contribution for this vault is representational breadth. The paper helps connect high-speed autonomy to quadrupedal robotics in a way that feels native rather than incidental.

The main limitation of this ingest is textual access. I was able to recover robust bibliographic metadata directly from the PDF, but not a clean full-text extraction path in this workspace, so this note stays intentionally careful and high level.
