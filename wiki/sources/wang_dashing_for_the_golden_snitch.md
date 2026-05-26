---
tags: [source]
date: 2026-05-13
sources: 1
---

# Wang Dashing for the Golden Snitch Source

> Source: `raw/pdfs/Wang_Dashing_for_the_Golden_Snitch_Multi-Drone_Time-Optimal_Motion_Planning_with_Multi-Agent_Reinforcement_Learning.pdf`
> Paper: Dashing for the Golden Snitch: Multi-Drone Time-Optimal Motion Planning with Multi-Agent Reinforcement Learning, ICRA 2025

## Summary

This paper studies time-optimal motion planning for multiple drones through a multi-agent reinforcement learning formulation.

For this vault, it matters because it brings together three themes that are usually split apart: aggressive time-optimal flight, explicitly multi-agent coordination, and learned planning rather than only learned control.

## Method

The paper frames multi-drone motion planning as a multi-agent reinforcement learning problem.

That framing is important because time-optimal flight in a shared space is not only a dynamics problem. It is also an interaction problem: each drone's best motion depends on what the others are doing, and that coupling grows quickly as the team size increases.

## Evaluation

The paper appears at ICRA 2025 and is clearly positioned at the intersection of agile drone motion planning and multi-agent RL.

For this vault, the key significance is architectural: it expands the drone-racing-adjacent branch from single-agent time trials and pursuit-evasion toward explicitly cooperative or competitive multi-drone time-optimal planning.

## Notes / Critique

The strongest contribution is the move from isolated fast flight to coordinated fast flight. That is exactly the sort of scaling step the field will need if aerial autonomy is to progress from demos to richer multi-agent environments.

This source belongs naturally near [[autonomous_drone_racing]], [[reinforcement_learning]], and [[multi_agent_time_optimal_motion_planning]].

## Pages Created From This Source

- [[dashing_for_the_golden_snitch_multi_drone_time_optimal_motion_planning_with_multi_agent_reinforcement_learning]]
- [[multi_agent_time_optimal_motion_planning]]
