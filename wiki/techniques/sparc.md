---
tags: [technique]
date: 2026-05-08
sources: 1
---

# SPARC

## Definition

SPARC is a contextual reinforcement-learning approach for out-of-distribution adaptation. It trains a single policy to infer latent environment context from recent interaction history and to adjust behavior online without requiring explicit context labels at test time.

In racing, this is useful when the learned controller must survive changes in vehicle dynamics or related hidden parameters across unseen cars.

## Key Approach

[[out_of_distribution_generalization_with_a_sparc_racing_100_unseen_vehicles_with_a_single_policy]] presents SPARC as a simpler alternative to multi-stage context-adaptation methods.

Its key idea is single-phase training for online contextual adaptation:

- The policy learns from rollout history rather than explicit deployment-time context variables.
- Adaptation is folded directly into the policy-learning pipeline.
- The same policy is expected to remain useful across many unseen contextual variants.

This makes SPARC a robustness-oriented extension of [[reinforcement_learning]] rather than a separate planning framework.

## Relationship to End-to-End Racing

SPARC belongs near [[end_to_end_autonomous_racing]] because it improves the resilience of learned policies under distribution shift.

Compared with pure fixed-context racing RL, it trades some simplicity in the policy architecture for better robustness when the vehicle or environment differs from training conditions.

## Representative Papers

- [[out_of_distribution_generalization_with_a_sparc_racing_100_unseen_vehicles_with_a_single_policy]]

## Open Problems

Open questions include how well this style of contextual adaptation transfers to real vehicles, how much history is needed for reliable inference, and whether unified adaptation remains stable when perception shift and dynamics shift happen simultaneously.
