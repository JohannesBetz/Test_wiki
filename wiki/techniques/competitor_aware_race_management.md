---
tags: [technique]
date: 2026-05-07
sources: 1
---

# Competitor-Aware Race Management

## Definition

Competitor-aware race management is a long-horizon autonomous racing strategy formulation in which the agent optimizes energy deployment, pit decisions, and interaction timing against specific competitors rather than minimizing lap time in isolation.

It is especially useful in electric endurance racing, where aerodynamic drafting and battery constraints make race outcome depend on who the car is racing, not just how fast it can drive alone.

## Key Approach

[[a_competitor_aware_race_management_policy_a_game_theoretical_approach]] implements this idea with a bi-level structure:

- A lower-level multi-agent game-theoretic optimal-control model for one lap.
- A learned surrogate of that single-lap interaction.
- An upper-level [[reinforcement_learning]] policy that allocates battery energy and pit strategy over the full race.

The point is to separate local physics-rich interaction modeling from race-long strategic optimization.

## Relationship to Racing Planning

This technique belongs under [[autonomous_racing_planning]], but it sits above the usual local-planning layer. It is closer to behavioral planning and race strategy than to trajectory generation.

Compared with single-agent minimum-time planning, it explicitly values slipstreaming, defensive positioning, delayed overtakes, and energy-preserving actions that may look locally suboptimal but improve final race position.

## Representative Papers

- [[a_competitor_aware_race_management_policy_a_game_theoretical_approach]]

## Open Problems

Open questions include scaling beyond two agents, handling richer uncertainty in competitor behavior, integrating strategic race management with online local planners, and transferring these methods from simulation assumptions to real electric race cars.
