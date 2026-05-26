---
tags: [source]
date: 2026-05-22
sources: 1
---

# Radosavovic Real-World Locomotion RL Source

> Source: `raw/pdfs/Radosavovic_Realworld_Locomotion_RL.pdf`
> Paper: Real-World Humanoid Locomotion with Reinforcement Learning, Science Robotics 2024

## Summary

This paper studies whether large-scale model-free reinforcement learning can produce robust humanoid locomotion that transfers zero-shot from simulation into the real world.

For this vault, the paper matters because it is one of the clearest humanoid counterparts to the quadruped real-world RL successes already in the graph.

## Method

The system is trained with large-scale [[reinforcement_learning]] in randomized simulation and then deployed directly on a real humanoid without task-specific real-world fine-tuning.

For this vault, the important lesson is not a new algorithm name so much as a systems claim:

- sufficiently structured simulation randomization,
- large-scale policy learning,
- and disciplined deployment design

can produce real humanoid locomotion competence rather than only benchmark performance in simulation.

## Evaluation

According to the public paper record, the controller is deployed zero-shot on a real humanoid and demonstrates robust locomotion outside tightly controlled lab-only flat-ground settings.

For this vault, the key result is embodiment transfer: humanoid locomotion joins quadruped locomotion as a real-world RL success case rather than remaining a purely aspirational frontier.

## Notes / Critique

The strongest contribution is evidentiary. It gives the humanoid branch a serious real-world RL anchor instead of leaving most embodied high-dynamics evidence concentrated in drones and quadrupeds.

That makes it a strong complement to:

- [[rapid_locomotion_via_reinforcement_learning]],
- [[rma_rapid_motor_adaptation_for_legged_robots]],
- and [[attention_based_map_encoding_for_learning_generalized_legged_locomotion]].

## Pages Created From This Source

- [[real_world_humanoid_locomotion_with_reinforcement_learning]]
