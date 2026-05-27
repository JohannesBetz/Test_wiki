---
tags: [paper]
date: 2026-05-27
task: autonomous_racing
venue: "manuscript"
sources: 1
year: "2023"
topic:
  - autonomous_racing_planning
  - autonomous_vehicle_racing
tech_backbone: [model_predictive_control]
tech_representation: [dynamic_potential_games]
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
hardware_used: [cars_and_race_cars]
simulators_used: []
---

# Autonomous Racing With Dynamic Games

> Autonomous Racing With Dynamic Games | manuscript around 2023 | local PDF metadata incomplete

## Summary

This paper treats autonomous racing as a dynamic multi-agent game rather than only as trajectory optimization with reactive collision avoidance.

Its main contribution to the vault is the pairing of:

- [[dynamic_potential_games]] as the strategic formulation,
- and `RAPID` as a scalable planner for real-time racing interaction.

That makes it a valuable anchor in the game-theoretic planning branch of autonomous racing.

## Method

The local PDF makes the structure of the method fairly clear even though the bibliographic header is messy:

- the paper formulates the racing problem as a multi-agent dynamic game,
- introduces `dynamic potential games` as the key organizing idea,
- and then builds a scalable planner called `RAPID` on top of that formulation.

For this vault, the central methodological point is that overtaking, blocking, and lane-choice behavior are not treated as mere obstacle-avoidance side effects. They are treated as strategic outcomes of coupled multi-agent objectives.

This places the paper in an interesting position relative to nearby work:

- more explicitly game-theoretic than standard receding-horizon planners,
- more online and interaction-centric than offline raceline methods,
- and more structured than learned black-box racing policies.

## Key Results

The strongest result, from the vault's point of view, is representational rather than numerical:

**competitive autonomous racing can be framed as a scalable dynamic game without giving up real-time planning altogether.**

The presence of both simulation and hardware sections also makes the paper more credible than a purely theoretical game-construction note. It suggests the authors cared about whether the dynamic-game formulation could survive contact with actual racing execution.

## Hardware Used

- Racecar-style physical racing platform used in hardware experiments.
- The current page does not recover a cleaner platform name from the local PDF text layer.


## Related Work

This paper belongs directly near [[autonomous_racing_planning]].

Compared with [[alpha_racer_real_time_algorithm_for_game_theoretic_motion_planning_and_control_in_autonomous_racing_using_near_potential_function]], it appears to keep the game structure more explicit online rather than compressing it as aggressively into an offline-learned surrogate.

Compared with [[strategizing_at_speed_a_learned_model_predictive_game_for_multi_agent_drone_racing]], it is the ground-racing counterpart: the same broader ambition of real-time multi-agent strategic planning, but in a vehicle-racing context.

## Notes / Critique

The most appealing part of this paper is that it takes competition seriously as a planning problem.

The main caveat is computational realism. Dynamic-game formulations often look elegant on paper and become fragile when the number of agents, maneuver branches, or uncertainty sources grows.

So the real question is not whether dynamic games are conceptually right. It is whether the scalable approximation remains strong enough when racing gets crowded, noisy, and fast.
