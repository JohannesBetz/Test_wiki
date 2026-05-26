---
tags: [source]
date: 2026-05-26
sources: 1
---

# Hermansdorfer Benchmarking Man Vs Machine Source

> Source: `raw/pdfs/Hermansdorfer_Benchmarking_Man_Vs_Machine.pdf`
> Paper: Benchmarking of a software stack for autonomous racing against a professional human race driver, EVER 2020

## Summary

This paper studies how an autonomous racing software stack compares against a professional human race driver when evaluated with motorsport-style data analysis rather than only software-internal metrics.

For this vault, it matters because it is one of the clearest early `human benchmark` papers in autonomous racing: not a simulator comparison, not an abstract survey claim, but a direct professional-driver reference point for a full autonomous racing stack.

## Method

The paper compares a professional race driver and an autonomous racing software stack using motorsport telemetry analysis methods.

For this vault, the important point is that the goal is diagnostic rather than celebratory. The comparison is used to identify where the software still lags human expert performance and which capability gaps matter most for future system development.

## Evaluation

The public abstract states that the paper focuses on extreme combined braking and steering situations near the limits of handling and uses the professional driver as the benchmark for extracting actionable weaknesses in the autonomous stack.

The broader takeaway is that human-versus-machine comparison can be scientifically useful when it is treated as structured systems diagnosis rather than only as a publicity race.

## Notes / Critique

The strongest contribution is the benchmarking frame itself. The paper treats the professional human driver not merely as an opponent, but as a measurement instrument for where autonomous racing software still fails to match expert limit handling.

That makes it a natural bridge between:

- [[professional_race_driver_expertise]], which studies what human experts actually do,
- [[challenging_f1_drivers_in_physical_race_cars_with_human_inspired_online_learning]], which tries to operationalize some of that skill,
- and [[accelerating_autonomy_insights_from_pro_racers_in_the_era_of_autonomous_racing]], which later deepens the human-skill analysis.

## Pages Created From This Source

- [[benchmarking_of_a_software_stack_for_autonomous_racing_against_a_professional_human]]
