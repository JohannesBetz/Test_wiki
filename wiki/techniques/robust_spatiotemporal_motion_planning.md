---
tags: [technique]
date: 2026-05-20
sources: 1
---

# Robust Spatiotemporal Motion Planning

## Definition

Robust spatiotemporal motion planning is a local planning approach that chooses maneuvers by reasoning over how collision-free corridors evolve through both space and time, rather than only checking whether a geometric path is free at one instant.

In autonomous racing, this is especially useful in overtaking and dense interaction scenarios where the right maneuver depends on whether a gap will remain usable long enough to exploit safely.

## Key Approach

[[robust_spatiotemporal_motion_planning_for_multi_agent_autonomous_racing_via_topological_gap_identification_and_accelerated_mpc]] is the anchor paper for this technique in the vault.

The method, as indicated by the paper title, combines:

- topological gap identification among nearby agents,
- robust space-time reasoning over candidate corridors,
- and accelerated [[model_predictive_control]] for real-time maneuver generation or execution.

The important shift is representational:

the planner does not ask only "which path is open now?" but "which topological corridor is likely to remain executable as all agents keep moving?"

## Relationship to Racing Planning

This technique belongs inside [[autonomous_racing_planning]], especially the local multi-agent planning layer.

Compared with [[multi_stage_time_variant_motion_planning]], it leans more toward explicit corridor reasoning and less toward broad staged sampling of maneuver primitives.

Compared with [[dynamic_near_potential_functions]], it leans more toward robust space-time feasibility than approximate dynamic-game structure.

Compared with [[risk_averse_model_predictive_control]], it addresses interaction-topology robustness more than parametric dynamics uncertainty.

## Representative Papers

- [[robust_spatiotemporal_motion_planning_for_multi_agent_autonomous_racing_via_topological_gap_identification_and_accelerated_mpc]]

## Open Problems

Open problems include how to identify topological gaps reliably under noisy perception, how to scale corridor reasoning to denser traffic, how to trade off early commitment against delayed optionality, and how to couple space-time gap reasoning with opponent-intent prediction rather than treating other agents as purely reactive movers.
