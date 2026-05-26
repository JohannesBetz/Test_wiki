---
tags: [source]
date: 2026-05-20
sources: 1
---

# Zhang Robust Spatiotemporal Planning Source

> Source: `raw/pdfs/Zhang_Robust_Spatiotemporal_Planning.pdf`
> Paper: Robust Spatiotemporal Motion Planning for Multi-Agent Autonomous Racing via Topological Gap Identification and Accelerated MPC, arXiv 2026

## Summary

This paper studies multi-agent autonomous racing from the planning side, focusing on how a racecar should generate robust spatiotemporal maneuvers when several nearby agents compete for limited free space.

The title already makes the structure clear: the method combines topological gap identification with accelerated MPC so the planner can reason about not only geometric free space, but about temporally usable passing corridors under real-time racing constraints.

## Method

The central technique is best represented here as [[robust_spatiotemporal_motion_planning]].

Within that umbrella, the paper appears to combine:

- explicit identification of topological free-space gaps among nearby agents,
- spatiotemporal reasoning over how those gaps evolve,
- and an accelerated [[model_predictive_control]] layer for real-time trajectory generation or tracking.

That places the paper naturally near the vault's local multi-agent planning branch rather than purely global raceline optimization or purely learned interaction policy work.

## Evaluation

Even before a full text extraction, the contribution is legible at the vault level: this is a robust multi-agent racing planner, so the key question is whether explicit gap-aware spatiotemporal reasoning improves overtaking and collision avoidance under tight runtime budgets.

That makes it a useful contrast with:

- [[multi_stage_time_variant_motion_planning]], which also addresses agile local maneuvers through staged sampling,
- [[dynamic_near_potential_functions]], which compresses game-theoretic maneuver selection into a learned surrogate,
- and [[risk_averse_model_predictive_control]], which emphasizes uncertainty and tail-risk handling more than maneuver-topology reasoning.

## Notes / Critique

The most interesting conceptual contribution is the move from generic obstacle avoidance toward topological corridor reasoning in dense racing interaction.

The local metadata was clean enough to recover title, authors, and arXiv DOI, but I did not have a reliable full-text extraction tool in this workspace, so this source note stays careful and method-level rather than pretending to reconstruct every experiment.

## Pages Created From This Source

- [[robust_spatiotemporal_motion_planning_for_multi_agent_autonomous_racing_via_topological_gap_identification_and_accelerated_mpc]]
- [[robust_spatiotemporal_motion_planning]]
