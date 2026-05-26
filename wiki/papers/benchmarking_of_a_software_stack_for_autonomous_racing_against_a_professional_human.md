---
tags: [paper]
date: 2026-05-26
task: autonomous_racing
venue: "2020 Fifteenth International Conference on Ecological Vehicles and Renewable Energies (EVER)"
sources: 1
bibtex_key: "Hermansdorfer2020"
bibtex_type: "inproceedings"
year: "2020"
doi: "10.1109/ever48776.2020.9242926"
url: "https://doi.org/10.1109/ever48776.2020.9242926"
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

# Benchmarking of a software stack for autonomous racing against a professional human race driver

> Benchmarking of a software stack for autonomous racing against a professional human race driver | 2020 Fifteenth International Conference on Ecological Vehicles and Renewable Energies (EVER) | Hermansdorfer et al. | BibTeX key: `Hermansdorfer2020`

## Summary

This paper asks how a professional human race driver and an autonomous racing software stack compare when analyzed through the lens of motorsport telemetry rather than only conventional autonomy metrics.

Its answer is a benchmark-style comparison designed to identify which parts of expert at-limit driving the autonomous stack still fails to match.

## Method

The paper compares a professional human race driver and an autonomous racing software stack using motorsport-style data analysis techniques.

From the public abstract, the focus is not just lap time, but how the software handles extreme combined braking and steering actions near the limit of handling.

For this vault, the important systems lesson is that a human benchmark can reveal much more than whether the machine is slower or faster. It can show where the machine's control, planning, or limit-handling behavior still differs qualitatively from expert human driving.

## Key Results

The public abstract says the comparison is used to derive indications for improving the software stack and to identify failure areas where the machine still does not meet professional-driver performance.

The most useful vault takeaway is broader than one benchmark:

**professional human drivers are valuable not only as performance targets, but as structured diagnostic baselines for autonomous racing software under extreme handling conditions.**

## Hardware Used

- [[cars_and_race_cars]]

## Related Work

- [[autonomous_vehicles_on_the_edge]]
- [[professional_race_driver_expertise]]
- [[accelerating_autonomy_insights_from_pro_racers_in_the_era_of_autonomous_racing]]
- [[challenging_f1_drivers_in_physical_race_cars_with_human_inspired_online_learning]]

## Notes / Critique

The strongest contribution is methodological. This is one of the vault's clearest early examples of using a professional human as a benchmark to inspect where an autonomous stack really stands at the handling limit.

The main caveat is that this note is anchored to the published abstract and canonical metadata rather than a clean local full-text parse. So I’ve kept it focused on the reliable benchmarking picture rather than claiming detailed telemetry findings the local file did not expose cleanly.
