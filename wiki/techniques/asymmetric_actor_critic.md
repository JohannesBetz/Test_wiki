---
tags: [technique]
date: 2026-05-07
sources: 1
---

# Asymmetric Actor-Critic

## Definition

An asymmetric actor-critic trains the critic with privileged information that is available in simulation, while constraining the actor or policy to use only observations available at deployment.

## Key Approaches

In [[outplaying_elite_table_tennis_players_with_an_autonomous_robot]], Ace's critic receives ground-truth ball state from the simulator, while the policy receives a history of noisy sensor measurements. This gives the critic a cleaner learning signal while forcing the deployed policy to handle real perception noise.

## Representative Papers

- [[outplaying_elite_table_tennis_players_with_an_autonomous_robot]]

## Open Problems

The key risk is a mismatch between what the privileged critic encourages and what the deployed actor can reliably infer from noisy observations. The technique works best when simulator noise models realistically cover deployment conditions.
