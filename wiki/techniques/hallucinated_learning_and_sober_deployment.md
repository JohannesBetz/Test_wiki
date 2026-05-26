---
tags: [technique]
date: 2026-05-20
sources: 1
---

# Hallucinated Learning and Sober Deployment

## Definition

Hallucinated learning and sober deployment is a navigation and control strategy in which the learning regime is intentionally more aggressive, imagination-heavy, or robustness-seeking than the eventual deployment regime, which is made more grounded and conservative for real-world execution.

In agile robot navigation, this is useful when the robot needs the benefits of hard or synthetic learning conditions without inheriting all of that optimism at deployment time.

## Key Approach

[[agile_robot_navigation_through_hallucinated_learning_and_sober_deployment]] is the anchor paper for this technique in the vault.

The important move is asymmetry:

- learn under more challenging or "hallucinated" conditions,
- deploy under a more careful or "sober" policy regime.

That means the technique does not assume that the best way to train a policy is also the best way to execute it on the physical robot.

## Relationship to Agile Navigation and Deployment

This technique belongs near [[cognitive_navigation]], [[real_world_robotic_reinforcement_learning]], and the broader [[Highly_dynamic_autonomous_system]] branch.

Compared with pure sim-to-real transfer, it frames the mismatch less as a nuisance and more as a deliberate design tool.

Compared with behavior-constrained RL, it appears to manage risk more through train-versus-deploy asymmetry than through explicit policy-space constraint alone.

## Representative Papers

- [[agile_robot_navigation_through_hallucinated_learning_and_sober_deployment]]

## Open Problems

Open problems include how much asymmetry between training and deployment is beneficial, how to keep the deployment regime conservative without erasing learned agility, how to measure when "hallucinated" learning improves robustness versus simply teaching artifacts, and how to generalize this strategy across different robot bodies and navigation tasks.
