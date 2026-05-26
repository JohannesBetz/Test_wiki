---
tags: [source]
date: 2026-05-26
sources: 1
---

# Long Hybrid Internal Model Source

> Source: `raw/pdfs/Long_HYBRID_INTERNAL_MODEL.pdf`
> Paper: Hybrid Internal Model: Learning Agile Legged Locomotion with Simulated Robot Response, ICLR 2024

## Summary

This paper studies how a legged robot can remain agile and robust with only minimal onboard sensing, without explicitly modeling terrain properties such as elevation, friction, or restitution.

For this vault, it matters because it offers a clean alternative to explicit terrain-modeling pipelines. Instead of trying to observe the environment in detail, the controller learns to infer disturbance through the robot's own response.

## Method

The core idea is a `Hybrid Internal Model` (`HIM`) based locomotion controller.

According to the project page and public abstract, the framework uses joint encoders and an IMU as the only sensors, then learns:

- an explicit velocity estimate,
- and an implicit latent response that captures stability and disturbance-relevant dynamics.

The latent is trained through contrastive learning so the controller can estimate environmental disturbance from partial noisy observations rather than from an explicit terrain map.

## Evaluation

The public record reports simulation and real-world experiments on Unitree quadruped robots, plus an additional simulator transfer to Cassie as a bipedal embodiment check.

For this vault, the main significance is not one benchmark number, but the design claim: strong legged agility may come from learning an internal response model rather than from richer exteroception.

## Notes / Critique

The strongest contribution is architectural. This is not just another RL locomotion paper; it is a statement that part of robust locomotion can be achieved by learning to simulate the robot's own response and infer disturbance from it.

That makes the paper a strong bridge among [[quadrupedal_locomotion]], [[reinforcement_learning]], and [[sim_to_real_transfer]].

## Pages Created From This Source

- [[hybrid_internal_model_learning_agile_legged_locomotion_with_simulated_robot_response]]
- [[hybrid_internal_model]]
