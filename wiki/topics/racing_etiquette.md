---
tags: [topic]
date: 2026-05-07
sources: 2
---

# Racing Etiquette

## Definition

Racing etiquette refers to the under-specified norms and sportsmanship rules that determine whether contact, blocking, passing, and defensive driving are considered acceptable.

## Key Approaches

[[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]] treats racing etiquette as a learning problem. The agent must be competitive but avoid behavior that human stewards would penalize. The authors tried to encode etiquette through collision penalties, rear-end penalties, and unsporting-collision penalties, then used human drivers and stewards to judge whether policies were too aggressive.

[[accelerating_autonomy_insights_from_pro_racers_in_the_era_of_autonomous_racing]] is not mainly about etiquette, but it helps explain the human side of racecraft: expert drivers use experience, visual cues, and vehicle feedback to decide when lines, curbs, braking points, and risk levels are acceptable.

## Representative Papers

- [[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]]
- [[accelerating_autonomy_insights_from_pro_racers_in_the_era_of_autonomous_racing]]

## Open Problems

Etiquette is contextual and subjective. Penalizing all collisions can make a racing agent timid, while precise blame modeling can still produce behavior humans judge as too aggressive. This is a useful case study for autonomous systems that must obey imprecise human norms.
