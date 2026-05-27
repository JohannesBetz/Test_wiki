---
tags: [source]
date: 2026-05-27
sources: 1
---

# Romero Dream2Fly Source

> Source: `raw/pdfs/Romero_Dream2Fly.pdf`
> Paper: Dream to Fly: Model-Based Reinforcement Learning for Vision-Based Drone Flight, ICRA 2026

## Summary

This paper presents **Dream to Fly**, a model-based reinforcement-learning system for aggressive drone flight that learns directly from onboard visual observations. Instead of relying primarily on a hand-engineered estimation and perception stack, it uses a learned world model to optimize control in latent space.

For this vault, it is a key adjacent result in the AGILEFLIGHT branch because it gives autonomous drone racing a strong `world-model MBRL from pixels` example, not only model-free RL or explicit state-estimation pipelines.

## Core Contribution

The paper's main shift is architectural:

- learn a latent world model from visual input,
- optimize policies against that world model,
- and map pixels to low-level flight commands with less explicit intermediate structure.

That makes it a useful counterpoint to [[champion_level_drone_racing_using_deep_reinforcement_learning]], where the final system remains more visibly hybrid in how perception and control are organized.

## Why It Matters Here

This source strengthens three recurring vault questions:

- how much of a high-speed autonomy stack can be learned end to end,
- whether world-model methods can outperform purely model-free approaches in aggressive embodied tasks,
- and how much interpretability or robustness is traded away when more of the stack is absorbed into latent learned structure.

It therefore belongs naturally near [[autonomous_drone_racing]], [[reinforcement_learning]], [[differentiable_simulation]], and [[learning_agile_quadrotor_flight_in_the_real_world]].

## Notes / Critique

The strongest point is that the paper pushes aggressive embodied control toward a more compact learned representation of the whole problem.

The likely weakness is the usual one for end-to-end visual control at high speed: once the stack becomes more latent and less modular, diagnosing failure under visual shift or edge cases becomes harder.

## Pages Created From This Source

- [[dream_to_fly_model_based_reinforcement_learning_for_vision_based_drone_flight]]
