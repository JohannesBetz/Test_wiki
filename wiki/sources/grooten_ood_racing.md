---
tags: [source]
date: 2026-05-08
sources: 1
---

# Grooten OOD Racing Source

> Source: `raw/pdfs/Grooten_OOD-racing.pdf`
> Paper: Out-of-Distribution Generalization with a SPARC: Racing 100 Unseen Vehicles with a Single Policy, AAAI-26

## Summary

This paper studies out-of-distribution generalization for learned control policies in autonomous racing and related continuous-control domains. Its central question is whether one reinforcement-learning policy can adapt online to previously unseen environment contexts, such as changed vehicle dynamics, without being given explicit context labels at test time.

For this vault, the paper is useful because it addresses one of the recurring weak points of end-to-end racing systems: they can be fast in-distribution but fragile when the vehicle, surface, or disturbance profile changes.

## Method

The paper introduces `SPARC`, a single-phase contextual reinforcement-learning method for latent environment adaptation. The key contrast is against two-stage context-adaptation pipelines such as RMA-style methods, where a context encoder and history-adaptation module are trained separately.

SPARC instead learns adaptation more directly in a unified setup. The policy uses interaction history to infer hidden context and adjust behavior online, aiming to preserve robustness without requiring explicit parameter identification during deployment.

## Evaluation

The paper evaluates the method in two settings:

- Autonomous racing in a high-fidelity Gran Turismo 7 environment with 100 unseen vehicle contexts.
- Wind-perturbed MuJoCo environments as a broader control benchmark.

The headline racing result is right in the title: one policy is able to race across 100 previously unseen vehicles. The paper frames this as reliable and robust OOD generalization rather than merely interpolation across lightly perturbed training variants.

## Notes / Critique

The strongest contribution is conceptual simplification. The paper takes a family of adaptation methods that can be awkward to train and compresses the idea into a cleaner single-phase workflow.

The main limitation is that it still lives inside simulation. It addresses distribution shift in learned racing policies, but not the full sim-to-real problem of perception noise, hardware delay, or track-specific sensing artifacts.

## Pages Created From This Source

- [[out_of_distribution_generalization_with_a_sparc_racing_100_unseen_vehicles_with_a_single_policy]]
- [[sparc]]
