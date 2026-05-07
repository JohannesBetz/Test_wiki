---
tags: [topic]
date: 2026-05-07
sources: 1
---

# Robot Table Tennis

## Definition

Robot table tennis studies robotic systems that perceive, plan, and hit table-tennis balls in real time, often against human opponents. It is a demanding benchmark for [[Highly_dynamic_autonomous_system|highly dynamic autonomous systems]] because the ball can be fast, highly spinning, and tactically shaped by the opponent.

## Key Approaches

- High-speed ball localization and spin estimation.
- Ball aerodynamics and bounce/contact modeling.
- Learned striking policies.
- Trajectory optimization for racket motion.
- Safe reset planning for the next shot.
- Serve generation and serve selection.
- Human opponent modeling and online adaptation.

## Representative Papers

- [[outplaying_elite_table_tennis_players_with_an_autonomous_robot]]

## Open Problems

The hardest open problems are returning professional-level high-spin shots, modeling human tactics, adapting online during a match, and training policies whose surrogate shot-level rewards reliably improve match-level win rate.
