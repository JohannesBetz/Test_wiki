---
tags: [source]
date: 2026-05-07
sources: 1
---

# Leng Expert Knowledge-Driven Racing Source

> Source: `raw/pdfs/Leng_ExpertKnowledge-drivenRacing.pdf`
> Paper: Expert Knowledge-driven Reinforcement Learning for Autonomous Racing via Trajectory Guidance and Dynamics Constraints, arXiv:2603.05842

## Summary

This paper proposes a hybrid reinforcement-learning method for autonomous racing that injects expert prior knowledge directly into policy learning. The method, `TraD-RL`, uses an expert racing line for trajectory guidance, explicit vehicle-dynamics constraints for safe operation, and a staged curriculum to move from guided learning toward limit exploration.

The paper is highly relevant to this vault because it sits between pure end-to-end RL and classical planning-and-control stacks. Instead of asking RL to discover everything from scratch, it narrows the search space with domain knowledge while still allowing the learned policy to exceed the original expert baseline.

## Method

The paper's three main ingredients are:

- Expert trajectory guidance: a prior racing line is folded into the state representation and reward shaping, helping stabilize early policy learning.
- Dynamics constraints: control-barrier-function-style safety envelopes encode explicit yaw-rate and sideslip limits so the learned policy stays in a physically plausible operating region.
- Multi-stage curriculum learning: the policy first learns stable guided behavior and later transitions toward autonomous high-speed exploration.

The authors describe this as a way to combine the exploration power of RL with the reliability of racing-domain priors.

## Evaluation

Experiments are conducted in a high-fidelity simulation environment modeled after the Berlin Tempelhof Airport Street Circuit. The paper reports that `TraD-RL` improves both lap speed and driving stability, and the ablation study argues that both trajectory guidance and dynamics constraints are essential.

The conclusion is especially clear: trajectory guidance raises the attainable racing limit by preventing conservative local optima, while explicit dynamics constraints suppress severe instability such as excessive yaw and sideslip.

## Notes / Critique

The strongest part is the structure of the hybridization. The paper does not merely add a safety penalty; it uses expert priors to shape the state, reward, exploration process, and safe operating region together.

The main limitation is that the validation is simulation-based. Like many racing RL papers, the argument for practical deployment will depend on how the guidance and constraint formulations transfer under model mismatch and real sensing noise.

## Pages Created From This Source

- [[expert_knowledge_driven_reinforcement_learning_for_autonomous_racing_via_trajectory_guidance_and_dynamics_constraints]]
- [[trajectory_guided_dynamics_constrained_reinforcement_learning]]
