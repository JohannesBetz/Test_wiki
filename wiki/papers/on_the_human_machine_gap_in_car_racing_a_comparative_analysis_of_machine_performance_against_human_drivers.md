---
tags: [paper]
date: 2026-05-26
task: autonomous_racing
venue: "IEEE Access 2024"
sources: 1
year: "2024"
doi: "10.1109/ACCESS.2024.3497719"
url: "https://doi.org/10.1109/ACCESS.2024.3497719"
topic:
  - autonomous_vehicle_racing
  - professional_race_driver_expertise
tech_backbone: [model_predictive_control]
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

# On the Human-Machine Gap in Car Racing: A Comparative Analysis of Machine Performance Against Human Drivers

> On the Human-Machine Gap in Car Racing: A Comparative Analysis of Machine Performance Against Human Drivers | IEEE Access 2024 | Eugenio Alcala and Victor Romero-Cano | DOI: 10.1109/ACCESS.2024.3497719

## Summary

This paper asks what still separates machine racing performance from human driving performance in car racing.

Its answer is a comparative analysis of machine performance against human drivers.

## Method

From the local metadata, the paper is organized around:

- autonomous racing,
- human-machine performance gap analysis,
- racing performance metrics,
- race-driving coaching,
- and [[model_predictive_control]].

For this vault, the important systems lesson is that the remaining gap should be analyzed across several performance dimensions rather than reduced to one headline result such as lap time.

## Key Results

The local metadata supports a broad reading: the paper treats the human-machine gap as a structured comparative problem and uses racing-performance metrics to analyze it.

The most useful vault takeaway is broader than one benchmark:

**autonomous racing progress should be judged not only by whether machines can occasionally match humans, but by which dimensions of racing competence still remain unevenly human.**

## Hardware Used

- [[cars_and_race_cars]]

## Related Work

This paper belongs directly near [[benchmarking_of_a_software_stack_for_autonomous_racing_against_a_professional_human]], but it appears broader and more comparative-analysis-oriented rather than focused on one software-stack benchmark.

Compared with [[accelerating_autonomy_insights_from_pro_racers_in_the_era_of_autonomous_racing]], it appears less interview- and expertise-extraction-centric and more metric- and performance-gap-centric.

Compared with [[challenging_f1_drivers_in_physical_race_cars_with_human_inspired_online_learning]], it appears less about closing the gap through online learning and more about characterizing what the gap actually is.

It also belongs near [[professional_race_driver_expertise]], because any serious account of the human-machine gap implicitly depends on what expert humans do differently at the limit.

## Notes / Critique

The strongest contribution is the framing. This paper gives the vault a more explicit `gap-analysis` anchor, which is useful because the field often oscillates between hype about isolated machine wins and vague claims that humans are still better.

The main caveat is that this ingest is anchored to robust local metadata rather than a clean full-text parse. So I’ve kept the note focused on the reliable comparative structure rather than detailed metric breakdowns the local file did not expose clearly.
