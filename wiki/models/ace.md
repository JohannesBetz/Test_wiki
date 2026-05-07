---
tags: [model]
date: 2026-05-07
sources: 1
---

# Ace

## Definition

Ace is the autonomous table-tennis robot introduced in [[outplaying_elite_table_tennis_players_with_an_autonomous_robot]]. It is designed for real-world competitive play against elite and professional humans under official table-tennis rules.

## Key Approaches

- 200 Hz 3D ball localization using APS cameras.
- 400-700 Hz spin estimation using [[event_based_vision]] gaze-control systems.
- Rally policies trained with [[soft_actor_critic]].
- [[asymmetric_actor_critic]] training for sim-to-real transfer from privileged simulator state to noisy real-world observations.
- Abstract learned actions mapped to collision-free trajectory optimization.
- Safe reset trajectories for dexterity and collision avoidance.
- Serve library created from human demonstrations, genetic-algorithm strike optimization, and real-robot expert evaluation.

## Representative Papers

- [[outplaying_elite_table_tennis_players_with_an_autonomous_robot]]

## Open Problems

Ace still lacks mature human opponent modeling and online learning. Better tactical adaptation could improve performance against professional players and reduce reliance on surrogate training objectives.
