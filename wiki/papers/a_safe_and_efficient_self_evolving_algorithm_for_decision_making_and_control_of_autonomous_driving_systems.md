---
tags: [paper]
date: 2026-05-08
task: autonomous_driving
venue: "IEEE Transactions on Intelligent Transportation Systems"
sources: 1
year: "2025"
doi: "10.1109/TITS.2025.3576372"
topic:
  - cognitive_navigation
tech_backbone: [reinforcement_learning, model_predictive_control]
tech_representation: []
tech_generation: [mechanism_experience_learning]
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
simulators_used: [carla]
---

# A Safe and Efficient Self-Evolving Algorithm for Decision-Making and Control of Autonomous Driving Systems

> A Safe and Efficient Self-Evolving Algorithm for Decision-Making and Control of Autonomous Driving Systems | IEEE T-ITS 2025 | Shuo Yang, Liwen Wang, Yanjun Huang, and Hong Chen

## Summary

This paper asks how an autonomous driving system can keep improving online-style through reinforcement learning without paying the usual price in unsafe exploration and low sample efficiency.

The answer is a hybrid architecture that combines constrained optimization, human-inspired driving preference modeling, and actor-critic reinforcement learning. Instead of letting RL discover safe behavior from scratch, the paper inserts safety structure directly into the policy generator.

## Method

The key idea is [[mechanism_experience_learning]]. The policy approximator has three parts:

- a mechanistic traffic-interaction model that predicts the nearest impactful vehicles,
- a driving-tendency network that outputs a coarse directional preference inspired by human driving intuition,
- and a constrained nonlinear optimizer that turns that tendency into lateral and longitudinal control actions.

The optimization layer is MPC-like. It uses a kinematic vehicle model, terminal objectives derived from the interaction model, and hard constraints for kinematics, control increments, collision avoidance, and safe following distance.

The learning layer is based on soft actor-critic. The critic uses twin Q networks to reduce overestimation bias, while the actor updates the driving-tendency network so the optimizer is nudged toward safer and more efficient maneuver directions.

The practical point is that the learned tendency reduces the search space, while the mechanism layer keeps exploration collision-free.

## Key Results

The paper evaluates the method in CARLA three-lane highway scenarios with static obstacles and dense dynamic traffic.

The main reported claims are:

- training converges after roughly 4000 to 6000 steps,
- no collisions occur during the full training process,
- the method reaches 0 percent collision rate in the tested dynamic-traffic deployment experiments,
- and it performs better overall than a comparison MPC setup and a comparison soft actor-critic baseline.

The RL baseline can drive faster on average but still collides. The MPC baseline remains safe but shows less reasonable lane-change behavior and lower efficiency. The proposed hybrid method aims to sit between those extremes.

## Related Work

This paper is not an autonomous racing paper, but it is relevant to [[cognitive_navigation]] because it treats perception, interaction reasoning, decision making, and control as one closed-loop autonomy problem rather than as isolated modules.

It is also useful context for [[reinforcement_learning]] and [[model_predictive_control]]. Compared with pure RL, it narrows exploration through structured priors and hard constraints. Compared with pure MPC, it uses learning to shape higher-level maneuver preference rather than solving only a fixed hand-crafted objective.

For the racing vault, the main transfer is conceptual: this is another example of a hybrid autonomy stack that tries to preserve adaptability without surrendering safety or interpretability.

## Notes / Critique

The strongest part of the paper is the systems perspective. It treats safety and efficiency not as separate patches but as architectural design constraints on how learning is allowed to act.

The main caveat is breadth of evaluation. The scenarios are useful highway benchmarks, but they are still cleaner and more structured than the full open-world autonomy problem, and they are farther from racing than many other papers in the vault.
