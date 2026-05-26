---
tags: [source]
date: 2026-05-13
sources: 1
---

# Kawaharazuka Real-World Robot Foundation Models Source

> Source: `raw/pdfs/Kawaharazuka_Real-world robot applications of foundation models  a review.pdf`
> Paper: Real-world robot applications of foundation models: a review, Advanced Robotics 2024

## Summary

This paper reviews how foundation models are actually being used on physical robots rather than only in simulation or abstract agent benchmarks.

For this vault, it matters because it narrows the question from "can foundation models be useful?" to the more operational one: "which parts of embodied robotic systems can foundation models currently improve in the real world, and where do they still break?"

## Method

The paper is a review rather than an algorithm proposal. Its organizing lens is real-world deployment.

That makes it especially useful here. Many broad foundation-model papers stay at the level of multimodal reasoning or decision architecture. This review instead asks what happens when such models must survive sensor noise, embodiment, control latency, safety constraints, and messy physical execution.

## Evaluation

The main contribution is a deployment-centered synthesis. The paper surveys real-world robotic uses of foundation models and therefore functions as a maturity check on the current field.

For this vault, the important value is calibration: it helps separate genuine embodied progress from hype imported from web-scale language or vision benchmarks.

## Notes / Critique

The strongest contribution is practical framing. A foundation model that looks impressive in language or simulation may still be weak once it must guide perception, planning, or manipulation on a real robot.

This source fits naturally between [[foundation_models_for_intelligent_decision_making]], [[embodied_autonomous_intelligence]], and [[real_world_robotic_foundation_models]].

## Pages Created From This Source

- [[real_world_robot_applications_of_foundation_models_a_review]]
- [[real_world_robotic_foundation_models]]
