---
tags: [paper]
date: 2026-05-27
task: human_performance
venue: "Sensors"
sources: 1
year: "2022"
doi: "10.3390/s22093542"
url: "https://doi.org/10.3390/s22093542"
topic:
  - driver_reaction_time
  - professional_race_driver_expertise
tech_backbone: []
tech_representation: []
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

# Evaluation of Driver Reaction Time

> Evaluation of Driver Reaction Time | Sensors | Tomas Culik et al.

## Summary

This paper evaluates driver reaction time in a driving simulator, focusing especially on young drivers and on how reaction time changes with variables such as experience, gender, and alcohol. It is primarily a road-safety and human-factors paper rather than a racing or autonomy paper.

For this vault, its importance is comparative: it gives a concrete human-performance reference for one of the hidden bottlenecks in high-speed driving and reaction-critical autonomy.

## Method

The paper uses simulator-based driving experiments with several controlled scenarios, including:

- unexpected obstacles,
- expected obstacles,
- subjective impressions from the simulation,
- and alcohol-impaired driving tests for a subset of drivers.

The study then applies standard statistical tests to determine which driver attributes significantly affect reaction time.

## Why It Matters

The vault often talks about:

- short reaction times in [[Highly_dynamic_autonomous_system]],
- human limit handling in [[professional_race_driver_expertise]],
- and perception-latency bottlenecks in [[high_speed_perception]].

This paper is useful because it gives a more explicit human baseline for that discussion. Even if the domain is road-safety simulation rather than racing, it helps make clear that human driving is bounded by a biological perception-to-action loop that autonomous systems may exceed, match, or fail to use effectively.

## Hardware Used

- [[cars_and_race_cars]] (driving simulator context)


## Related Work

This paper belongs closest to [[driver_reaction_time]] and [[professional_race_driver_expertise]].

Compared with the pro-racer and human-versus-machine papers in the vault, it is less about elite driving skill and more about generic human response timing. That narrower focus is still useful because reaction time is one of the raw ingredients underneath both everyday safety and high-performance driving.

## Notes / Critique

The best use of this paper in the vault is as background context, not as a direct benchmark against autonomous systems. Simulator reaction-time studies capture an important human limitation, but they do not by themselves describe elite race-driver anticipation or the richer sensorimotor strategies experts use to avoid relying on raw reflex alone.
