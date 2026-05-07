---
tags: [topic]
date: 2026-05-06
sources: 7
---

# Highly Dynamic Autonomous System

## Definition

Highly dynamic autonomous systems are autonomous robots or vehicles that operate with high speed, high acceleration, short reaction times, nonlinear dynamics, and tight safety margins.

## Key Approaches

This topic connects [[autonomous_vehicle_racing]] to adjacent agile robotics domains such as drones, humanoids, quadrupeds, and other systems that must perceive, plan, and control near dynamic limits.

[[champion_level_drone_racing_using_deep_reinforcement_learning]] adds a concrete drone-racing example: onboard-only perception, real-time learned control, and sim-to-real transfer on a physical quadrotor racing at champion level.

[[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]] adds a high-fidelity simulator example where real-time control is coupled with human interaction, multi-agent tactics, and imprecise social/sportsmanship rules.

[[outplaying_elite_table_tennis_players_with_an_autonomous_robot]] adds a physical human-robot interaction example: real-time event-based spin perception, learned robot control, safe trajectory generation, and official-rules matches against elite and professional table-tennis players.

[[gripmap_an_efficient_spatially_resolved_constraint_framework_for_offline_and_online_trajectory_planning_in_autonomous_racing]] adds a constraint-awareness example: highly dynamic systems may need spatially local models of what their body, controller, and environment can safely support, not only a global dynamics model.

[[accelerating_autonomy_insights_from_pro_racers_in_the_era_of_autonomous_racing]] adds a human-skill lens: expert operators often combine multisensory feedback, experience, and rapid exploration to discover the usable dynamic envelope under sparse data.

[[challenging_f1_drivers_in_physical_race_cars_with_human_inspired_online_learning]] adds a physical-system learning example: [[apex]] learns performance constraints online while keeping exploration bounded by interpretable safety indicators.

## Representative Papers

- [[autonomous_vehicles_on_the_edge]]
- [[champion_level_drone_racing_using_deep_reinforcement_learning]]
- [[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]]
- [[outplaying_elite_table_tennis_players_with_an_autonomous_robot]]
- [[gripmap_an_efficient_spatially_resolved_constraint_framework_for_offline_and_online_trajectory_planning_in_autonomous_racing]]
- [[accelerating_autonomy_insights_from_pro_racers_in_the_era_of_autonomous_racing]]
- [[challenging_f1_drivers_in_physical_race_cars_with_human_inspired_online_learning]]

## Open Problems

The first baseline from autonomous racing points to high-speed perception, multi-agent planning, adversarial interaction, real-time dynamics modeling, and safety-performance tradeoffs as reusable research problems across highly dynamic autonomy.

The Swift result adds robustness gaps that matter across agile systems: appearance change, crash recovery, opponent-aware strategy, and adaptation beyond a known course.

Ace adds another transfer gap: in real-time human-robot sports, the real objective is match outcome, but training often relies on surrogate shot-level rewards because human opponent behavior is difficult to model in simulation.

GripMap adds a localization of uncertainty problem: the usable dynamic envelope can vary across space, and systems need ways to learn or update those local constraints without becoming too conservative everywhere.

Professional-racer interviews add a learning-speed problem: highly dynamic autonomy still lacks the few-shot adaptability expert humans show when conditions change.
