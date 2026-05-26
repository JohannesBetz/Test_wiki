---
tags: [source]
date: 2026-05-22
sources: 1
---

# He Attention-Based Locomotion Source

> Source: `raw/pdfs/He_Attentiopn_based_Locomotion.pdf`
> Paper: Attention-Based Map Encoding for Learning Generalized Legged Locomotion, Science Robotics 2025

## Summary

This paper studies how a learning-based legged controller can stay robust on diverse terrain without giving up the precision needed for sparse footholds, jumps, crouching maneuvers, and other structured locomotion challenges.

For this vault, the paper matters because it proposes a shared perceptive-locomotion idea that works across different legged bodies rather than only on one robot morphology.

## Method

The core idea is [[attention_based_map_encoding]].

The controller conditions an attention-based terrain representation on robot proprioception, then trains the full policy end to end with [[reinforcement_learning]].

The learned map encoder helps the policy focus on steppable and task-relevant terrain structure rather than treating the whole local map as equally important.

## Evaluation

According to the paper metadata and abstract, the method is demonstrated on both a 12-degree-of-freedom quadrupedal robot and a 23-degree-of-freedom humanoid robot, with real-world tests across difficult indoor and outdoor terrain that includes scenarios unseen during training.

For this vault, the important result is not only robustness but embodiment breadth: the same perceptive-control idea is shown to transfer across legged robot classes.

## Notes / Critique

The strongest contribution is that the paper turns terrain perception into a selective representation problem. Instead of feeding terrain maps naively into a policy, it learns where the controller should look.

That makes it a strong complement to:

- [[learning_robust_perceptive_locomotion_for_quadrupedal_robots_in_the_wild]], which emphasizes robust learned perceptive control on a quadruped,
- [[perceptive_locomotion_through_nonlinear_model_predictive_control]], which emphasizes a model-based perceptive-control alternative,
- and [[real_world_robotic_reinforcement_learning]], where this paper adds a rare cross-embodiment real-world RL result.

## Pages Created From This Source

- [[attention_based_map_encoding_for_learning_generalized_legged_locomotion]]
- [[attention_based_map_encoding]]
