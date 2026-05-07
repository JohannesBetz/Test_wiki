---
tags: [source]
date: 2026-05-07
sources: 1
---

# Werner Challenging F1 Drivers Source

> Source: `raw/pdfs/Werner_Challenging_F1_drivers.pdf`

## Summary

This manuscript introduces [[apex|APEX]], a human-inspired online learning framework for operating physical race cars near their performance limits. APEX learns a spatially resolved performance envelope for the combined vehicle-control system and uses that envelope to adapt planning and control constraints online.

The paper builds directly on [[professional_race_driver_expertise]], [[g_g_g_v_diagrams]], and [[gripmap]]. It translates expert-driver learning into three machine principles: experience-driven initialization, observation-driven adaptation, and anticipation-driven prediction.

## Method

APEX has four layers:

- Experience layer: a fixed [[g_g_g_v_diagrams|G-G-G-V]] reference model distilled from a higher-fidelity two-track model.
- Observation layer: independent observer modules monitor vehicle and controller stress indicators such as tire slip, slip angle, combined slip, velocity error, lateral acceleration error, lateral path deviation, and ESC/TC/ABS intervention.
- Anticipation layer: predictor modules estimate expected performance shifts from measurable state changes; the paper implements a tire-temperature predictor.
- Fusion layer: an explorator fuses observer and predictor outputs into a spatial performance map `theta(s,n)` using the [[gripmap]] representation.

The learned `theta(s,n)` scales the reference model and supplies updated constraints to an online velocity planner and a robustified control stack. The design is intentionally source-agnostic: `theta` is not a pure friction estimate, but a local correction of the executable closed-loop performance envelope.

## Evaluation

In simulation, APEX learns local constraints over repeated laps and outperforms globally uniform reference-model scaling. On uniform grip, APEX reaches 57.93 s versus 58.52 s for the best global scaling run. With turn-by-turn varying grip, APEX reaches 58.21 s versus 59.38 s for global scaling. Adding a tire-temperature predictor reduces convergence time from about 7-8 laps to about 4-5 laps.

In physical-car validation, APEX is evaluated against Formula 1 drivers. At the Mercedes-Benz Immendingen handling course, APEX reaches 1:59.23 in a Mercedes-AMG GT 63 S, 1.46 s or 1.2% slower than George Russell's 1:57.77. At A2RL 2025 on Yas Marina North, TUM Autonomous Motorsport's vehicle Hailey sets a 58.183 s autonomous race lap, 0.61 s or 1.07% slower than Daniil Kvyat's 57.569 s.

During the A2RL grand final, APEX also sets the fastest autonomous race lap and adapts through race interruptions and tire-temperature changes. The paper reports six weeks of testing, 58 sessions, and 2000 km driven with APEX continuously enabled without spins, crashes, or tire-set losses from flat-spotting.

## Notes / Critique

The main significance is that APEX turns [[gripmap]] from a static spatial constraint representation into an online learned performance envelope. It is interpretable and modular, unlike end-to-end RL, but still captures repeated local residuals that fixed model-based planners miss.

The main limitation is causal ambiguity. The learned scaling factor mixes local grip, model error, actuator limits, and controller residuals. This is useful for planning feasibility, but weaker for physical explanation or extrapolation far away from previously driven trajectories.

## Pages Created From This Source

- [[challenging_f1_drivers_in_physical_race_cars_with_human_inspired_online_learning]]
- [[apex]]
- [[abu_dhabi_autonomous_racing_league]]
