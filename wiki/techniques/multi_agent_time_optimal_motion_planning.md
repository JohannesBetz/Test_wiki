---
tags: [technique]
date: 2026-05-13
sources: 1
---

# Multi-Agent Time-Optimal Motion Planning

## Definition

Multi-agent time-optimal motion planning is a planning approach in which several embodied agents jointly optimize motion to minimize time while respecting interaction, collision, and shared-space constraints.

## Key Approach

[[dashing_for_the_golden_snitch_multi_drone_time_optimal_motion_planning_with_multi_agent_reinforcement_learning]] applies this idea to multiple drones through a multi-agent reinforcement learning framework.

The core challenge is that time-optimality becomes coupled across agents. One agent's fastest motion can block, constrain, or reshape another's feasible plan, so planning must account for interaction rather than treat the others as static obstacles.

## Relationship to High-Speed Aerial Autonomy

This technique belongs near [[autonomous_drone_racing]], [[reinforcement_learning]], and the broader multi-agent side of [[Highly_dynamic_autonomous_system]].

Compared with single-agent time-optimal planning, it is less about pushing one platform to the limit in isolation and more about negotiating several dynamic envelopes at once.

## Representative Papers

- [[dashing_for_the_golden_snitch_multi_drone_time_optimal_motion_planning_with_multi_agent_reinforcement_learning]]

## Open Problems

Open problems include scaling to larger drone teams, balancing time optimality against safety and communication limits, handling partial observability, and deciding when learned coordination should be preferred over more structured distributed planning methods.
