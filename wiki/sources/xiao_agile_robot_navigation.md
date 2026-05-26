---
tags: [source]
date: 2026-05-20
sources: 1
---

# Xiao Agile Robot Navigation Source

> Source: `raw/pdfs/Xiao_Agile_Robot_Navigation_through_Hallucinated_Learning_and_Sober_Deployment.pdf`
> Paper: Agile Robot Navigation through Hallucinated Learning and Sober Deployment

## Summary

This paper appears to study agile robot navigation with a training-to-deployment split that is already very suggestive from the title: aggressive or "hallucinated" learning on one side, and more careful or "sober" deployment on the other.

That makes it relevant to the vault because it speaks to a recurring autonomy problem:

- how to train for agility and ambition,
- without deploying a controller that is recklessly optimistic in the real world.

## Method

The central method is best represented here as [[hallucinated_learning_and_sober_deployment]].

From the title, the key idea appears to be a deliberate asymmetry:

- training uses more aggressive, imagination-heavy, or robustness-seeking learning assumptions,
- deployment uses a more conservative execution mode designed to remain reliable on the real robot.

This places the paper near:

- agile navigation,
- sim-to-real and deployment-robust autonomy,
- and the broader question of how to preserve learned agility without importing training-time optimism directly into physical execution.

## Evaluation

At the vault level, the key evaluation question is whether this train-hard, deploy-carefully structure improves real agile navigation performance while avoiding brittle real-world failures.

That makes it a useful complement to other papers in the vault where performance depends on keeping adaptation, learning, and deployment discipline in balance.

## Notes / Critique

The most interesting conceptual contribution is the explicit acknowledgment that the best training regime and the best deployment regime may not be the same.

The local metadata was sparse, but the title and authorship were recoverable. I did not have a clean full-text extraction path in this workspace, so this source note stays careful and method-level rather than pretending to reconstruct every algorithmic detail.

## Pages Created From This Source

- [[agile_robot_navigation_through_hallucinated_learning_and_sober_deployment]]
- [[hallucinated_learning_and_sober_deployment]]
