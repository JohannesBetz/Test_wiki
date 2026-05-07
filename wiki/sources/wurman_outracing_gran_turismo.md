---
tags: [source]
date: 2026-05-07
sources: 1
---

# Outracing Gran Turismo Source

> Source: `raw/pdfs/Wurman_Outracing_GranTurismo.pdf`

## Summary

This Nature paper introduces [[gt_sophy|Gran Turismo Sophy]], a deep reinforcement learning agent that beat top human Gran Turismo Sport drivers in both time-trial and head-to-head team racing. The work is important for [[autonomous_vehicle_racing]] because it treats high-performance racing as a combined problem of vehicle control, multi-agent tactics, sportsmanship norms, and strategy.

Unlike many autonomous racing systems that separate trajectory planning, tracking, and behavior, GT Sophy learns a single integrated policy through [[quantile_regression_soft_actor_critic]] and [[mixed_scenario_training]]. The policy controls throttle/brake and steering at 10 Hz while observing detailed vehicle state, track geometry, and nearby opponent state through the Gran Turismo API.

## System

GT Sophy was trained in [[gran_turismo_sport]] using distributed PlayStation rollout workers. The agent received:

- A static track map encoded as upcoming left-edge, centerline, and right-edge points in the car's egocentric frame.
- Vehicle state such as velocity, acceleration, angular velocity, tyre load, and tyre slip.
- Nearby opponent positions, velocities, accelerations, and slipstream information.

The reward combined course progress, off-course penalties, wall penalties, tyre-slip penalties, passing rewards, collision penalties, rear-end penalties, and unsporting-collision penalties. This reward design is one of the paper's central contributions because it makes the agent fast while discouraging unacceptable racing behavior.

## Key Results

- GT Sophy achieved superhuman time-trial performance on Seaside, Maggiore, and Sarthe.
- In July 2021, human drivers won the initial head-to-head team event 86-70.
- After training and design improvements, GT Sophy won the October 2021 rematch 104-52.
- The agent learned contextual racing tactics: corner passing, slipstream use, blocking, draft disruption, and emergency maneuvers.
- The authors identify remaining weakness in high-level race strategy: GT Sophy sometimes passed too early or attacked cars that would soon serve penalties.

## Notes / Critique

GT Sophy is not a physical robot, but the simulator's vehicle dynamics and multi-agent racing structure make it highly relevant to [[Highly_dynamic_autonomous_system|highly dynamic autonomous systems]]. Its most transferable lessons are about learning tactics under human norms, exposing rare race situations during training, and balancing speed against collision/sportsmanship costs.

The paper also highlights fairness asymmetries. GT Sophy had precise state and opponent information, full rear visibility, and low reaction latency, while human drivers had richer visual context, smoother controls, gear shifting, traction control, and real racing judgment.

## Pages Created From This Source

- [[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]]
- [[gt_sophy]]
- [[gran_turismo_sport]]
- [[quantile_regression_soft_actor_critic]]
- [[mixed_scenario_training]]
- [[racing_etiquette]]
