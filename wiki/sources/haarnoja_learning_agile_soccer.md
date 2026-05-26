---
tags: [source]
date: 2026-05-22
sources: 1
---

# Haarnoja Learning Agile Soccer Source

> Source: `raw/pdfs/Haarnoja_Learning_agile_Soccer.pdf`
> Paper: Learning Agile Soccer Skills for a Bipedal Robot with Deep Reinforcement Learning, Science Robotics 2024

## Summary

This paper studies how a small bipedal robot can learn agile soccer skills through deep reinforcement learning rather than relying only on manually engineered skills and scripted behavior.

For this vault, the paper matters because it adds a sports-like, contact-rich humanoid agility case that sits somewhere between locomotion, manipulation, and multi-object interaction.

## Method

From the local traces and linked project references, the system is trained with [[reinforcement_learning]] and transferred to the physical ROBOTIS OP3 platform.

For this vault, the important point is not only that the robot walks, but that it learns ball-relevant agile behaviors in a dynamic task setting where locomotion has to stay coordinated with external-object interaction.

## Evaluation

The embedded metadata and links indicate a real-robot deployment on OP3 and a public project page for the soccer result.

For this vault, the useful takeaway is that agile bipedal skill learning is not limited to traversal benchmarks. Competitive or game-like interaction tasks can also serve as strong embodied testbeds.

## Notes / Critique

The strongest contribution is domain broadening. It gives the humanoid branch a dynamic skill-learning example that is not only about terrain traversal or parkour.

That makes it a strong complement to:

- [[real_world_humanoid_locomotion_with_reinforcement_learning]],
- [[humanoid_parkour_learning]],
- and [[perceptive_humanoid_parkour_chaining_dynamic_human_skills_via_motion_matching]].

## Pages Created From This Source

- [[learning_agile_soccer_skills_for_a_bipedal_robot_with_deep_reinforcement_learning]]
