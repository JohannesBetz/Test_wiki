---
tags: [paper]
date: 2026-05-20
task: mobile_robot_navigation
venue: "manuscript / local PDF"
sources: 1
year: "2026"
topic:
  - cognitive_navigation
  - Highly_dynamic_autonomous_system
  - real_world_robotic_reinforcement_learning
tech_backbone: []
tech_representation: [hallucinated_learning_and_sober_deployment]
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
hardware_used: [mobile_robots]
simulators_used: []
---

# Agile Robot Navigation through Hallucinated Learning and Sober Deployment

> Agile Robot Navigation through Hallucinated Learning and Sober Deployment | Xuesu Xiao

## Summary

This paper appears to ask a very practical embodied-autonomy question: how can a robot be trained for agile navigation without deploying the same level of optimism or hallucinated confidence that may have been useful during learning?

Its answer, as signaled by the title, is to separate aggressive learning from conservative deployment.

## Method

The paper's central idea is captured here as [[hallucinated_learning_and_sober_deployment]].

At a high level, the title suggests a two-phase structure:

- a training regime that deliberately exposes the policy to harder, more aggressive, or more imagination-driven conditions,
- and a deployment regime that tempers this learned aggressiveness with more grounded execution logic.

This makes the paper a natural bridge between:

- [[real_world_robotic_reinforcement_learning]], where deployment is the real test,
- [[cognitive_navigation]], where navigation must remain a coherent perception-decision-execution loop,
- and the broader highly-dynamic autonomy branch, where overoptimistic learned behavior can fail very quickly in the physical world.

## Key Result

At the vault level, the key result is conceptual:

**agile robot navigation may improve when training is allowed to be more adventurous than deployment, rather than forcing one identical behavior regime to serve both learning and real-world execution.**

That matters because many embodied systems need the benefits of aggressive learning, but cannot afford the exact same risk profile once deployed.

## Hardware Used

- [[mobile_robots]]


## Related Work

Compared with papers that emphasize direct high-performance deployment, this paper appears to focus more explicitly on the training-deployment mismatch itself.

Compared with [[behavior_constrained_reinforcement_learning_with_receding_horizon_credit_assignment_for_high_performance_control]], it likely addresses a similar brittleness problem from a different angle: not by constraining learned behavior internally, but by making the deployment policy or regime more disciplined than the learning regime.

Compared with [[champion_level_drone_racing_using_deep_reinforcement_learning]], it likely contributes less to absolute racing-style peak performance and more to the broader question of how learned agile navigation survives deployment.

## Notes / Critique

The strongest idea is the asymmetry itself. It treats deployment caution not as a failure of learning, but as an intentional part of the autonomy design.

The main caveat of this ingest is evidentiary: the local PDF metadata was sparse and I did not have a clean full-text extraction path in this workspace, so this note is intentionally careful and should be deepened later with fuller access to the paper text.
