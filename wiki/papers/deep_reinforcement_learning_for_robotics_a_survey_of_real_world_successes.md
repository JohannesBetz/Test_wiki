---
tags: [paper]
date: 2026-05-08
task: robotics
venue: "Annual Review of Control, Robotics, and Autonomous Systems"
sources: 1
year: "2025"
doi: "10.1146/annurev-control-030323-022510"
topic:
  - embodied_autonomous_intelligence
  - Highly_dynamic_autonomous_system
tech_backbone: [reinforcement_learning]
tech_representation: []
tech_generation: [real_world_robotic_reinforcement_learning]
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
hardware_used: [multiple_robot_embodiments]
simulators_used: []
---

# Deep Reinforcement Learning for Robotics: A Survey of Real-World Successes

> Deep Reinforcement Learning for Robotics: A Survey of Real-World Successes | Annual Review of Control, Robotics, and Autonomous Systems 2025 | Chen Tang, Ben Abbatematteo, Jiaheng Hu, Rohan Chandra, Roberto Martin-Martin, and Peter Stone

## Summary

This paper surveys deep reinforcement learning in robotics with a practical lens: not which DRL papers are most impressive in simulation, but which robotic capabilities have actually shown meaningful success in the physical world.

That framing matters for this vault because autonomous racing often sits in the same conversation as locomotion, manipulation, drone flight, and other embodied control problems, yet the maturity of DRL differs sharply across those domains.

## Method

The survey introduces a four-axis taxonomy:

- robot competencies learned with DRL,
- problem formulation,
- solution approach,
- and level of real-world success.

It divides competencies into single-robot abilities such as locomotion, navigation, stationary manipulation, and mobile manipulation, plus multi-agent abilities such as human-robot and multirobot interaction.

The paper then compares which combinations of these competencies and solution approaches have produced credible real-world results. A key feature is the explicit success-level scale, which separates simulation-only claims from controlled physical validation and from more robust deployment.

## Key Results

The survey argues that real-world DRL has genuinely succeeded in some important robotic domains, but unevenly.

Champion-level drone racing is one of the standout high-dynamic examples. The paper also highlights strong locomotion successes in quadrupeds and other embodied robots. By contrast, areas such as urban autonomous driving still show limited real-world DRL maturity and often remain confined to simulation or tightly controlled field tests.

Across domains, the paper emphasizes a recurring pattern: successful real-world DRL usually depends on more than an off-the-shelf RL algorithm. It often requires simulation-to-real transfer, strong inductive structure, careful reward and data design, and system-level engineering around the learner.

## Hardware Used

- [[multiple_robot_embodiments]]


## Related Work

For this vault, the paper connects naturally to [[reinforcement_learning]], [[embodied_autonomous_intelligence]], and [[Highly_dynamic_autonomous_system]]. It helps place racing-specific successes like [[champion_level_drone_racing_using_deep_reinforcement_learning]] inside a broader robotics map.

It also gives useful contrast with road-driving papers such as [[a_safe_and_efficient_self_evolving_algorithm_for_decision_making_and_control_of_autonomous_driving_systems]]. Those papers may show promising architectures, but this survey reminds us that the bar for real-world robotic maturity is higher than simulator competence or narrow demonstrations.

## Notes / Critique

The strongest aspect is the insistence on real-world evidence. That makes the paper more useful than a generic algorithm survey for anyone trying to judge whether a learning-based robotics claim is merely plausible or already operationally meaningful.

Its main weakness is that such breadth necessarily compresses detail. The survey is best used as a map of maturity and recurring design patterns, not as a substitute for reading the strongest domain-specific papers.
