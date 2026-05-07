---
tags: [simulator]
date: 2026-05-07
sources: 1
---

# Gran Turismo Sport

## Definition

Gran Turismo Sport is a PlayStation racing simulator with high-fidelity vehicle dynamics and competitive motorsport structure. In [[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]], it is the training and evaluation environment for [[gt_sophy]].

## Key Approaches

GT Sophy interacted with Gran Turismo Sport through an API, receiving vehicle, track, and opponent state and returning throttle/brake and steering commands. The game ran at a 60 Hz dynamics cycle, while GT Sophy acted at 10 Hz.

## Papers Using This

- [[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]]
- [[super_human_performance_in_gran_turismo_sport_using_deep_reinforcement_learning]]
- [[autonomous_overtaking_in_gran_turismo_sport_using_curriculum_reinforcement_learning]]
