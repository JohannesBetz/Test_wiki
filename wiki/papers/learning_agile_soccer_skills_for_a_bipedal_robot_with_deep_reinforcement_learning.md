---
tags: [paper]
date: 2026-05-22
task: robotics
venue: "Science Robotics"
sources: 1
year: "2024"
doi: "10.1126/scirobotics.adi8022"
url: "https://www.science.org/doi/10.1126/scirobotics.adi8022"
topic:
  - Highly_dynamic_autonomous_system
  - embodied_autonomous_intelligence
  - real_world_robotic_reinforcement_learning
tech_backbone: [reinforcement_learning]
tech_representation: []
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
hardware_used: [humanoids]
simulators_used: []
---

# Learning Agile Soccer Skills for a Bipedal Robot with Deep Reinforcement Learning

> Learning Agile Soccer Skills for a Bipedal Robot with Deep Reinforcement Learning | Science Robotics 2024 | Tuomas Haarnoja et al. | DOI: 10.1126/scirobotics.adi8022

## Summary

This paper asks whether deep reinforcement learning can produce agile soccer-relevant behaviors on a physical bipedal robot.

Its answer is yes: agile embodied skill can be learned on a soccer platform rather than being limited to pure locomotion or parkour benchmarks.

## Method

The paper uses [[reinforcement_learning]] as the core training backbone for a bipedal robot skill policy.

For this vault, the main architectural interest is the task setting: locomotion is not the end goal, but part of a larger ball-interaction skill loop. That makes the controller a useful example of dynamic embodied competence under object interaction rather than only terrain traversal.

## Key Results

The local metadata and project references support the main high-level claim that the result is demonstrated on the ROBOTIS OP3 bipedal robot in a real soccer-skills setting.

The most useful vault takeaway is broader than one soccer demo:

**agile embodied RL on humanoid-like platforms can be organized around interaction tasks, not only around getting from A to B over hard terrain.**

## Hardware Used

- [[humanoids]]

## Related Work

This paper belongs directly near [[real_world_humanoid_locomotion_with_reinforcement_learning]], but it shifts the target from locomotion stability to agile interaction skill.

Compared with [[humanoid_parkour_learning]], this paper is less about large obstacle traversal and more about agile behavior in a game-like task loop.

Compared with [[perceptive_humanoid_parkour_chaining_dynamic_human_skills_via_motion_matching]], it appears less focused on explicit skill chaining and more on learned embodied performance in a specific interaction domain.

It also belongs near [[embodied_autonomous_intelligence]], because soccer is a nice reminder that embodied skill is often about coordinating movement with external task objects under tight timing constraints.

## Notes / Critique

The strongest contribution is the domain shift: it shows that the humanoid RL branch should not be read only through locomotion and parkour.

The main caveat is that the local PDF traces were much weaker than the title suggests, so I’ve written this as a careful high-level placement anchored by the project link and metadata rather than as a detailed experiment-by-experiment reading.
