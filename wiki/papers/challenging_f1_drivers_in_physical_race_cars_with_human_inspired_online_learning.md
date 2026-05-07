---
tags: [paper]
date: 2026-05-07
task: autonomous_racing
venue: "manuscript"
sources: 1
year: "2026"
topic:
  - autonomous_racing
  - online_learning
  - trajectory_planning
  - motion_control
  - human_driver_benchmarking
tech_backbone: []
tech_representation: [g_g_g_v_diagrams, gripmap]
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: [abu_dhabi_autonomous_racing_league]
models_used: [apex]
simulators_used: []
---

# Challenging F1 Drivers in Physical Race Cars with Human-Inspired Online Learning

> Challenging F1 Drivers in Physical Race Cars with Human-Inspired Online Learning | Werner, Langmann, Buettner, Schwehn, Pitschi, Lienkamp, and Betz

## Summary

This paper introduces [[apex|APEX (Adaptive Performance Envelope eXploration)]], an online learning framework for autonomous racing. APEX adapts a spatial performance map of the executable vehicle-control envelope, allowing a modular autonomous racing stack to safely push closer to the limit over repeated laps.

The work is a direct algorithmic continuation of [[accelerating_autonomy_insights_from_pro_racers_in_the_era_of_autonomous_racing]], [[a_quasi_steady_state_black_box_simulation_approach_for_the_generation_of_g_g_g_v_diagrams]], and [[gripmap_an_efficient_spatially_resolved_constraint_framework_for_offline_and_online_trajectory_planning_in_autonomous_racing]]. It takes the human-driver idea of learning through experience, observation, and anticipation and turns it into a map-based adaptation architecture.

## Method

APEX decomposes online limit learning into four layers.

The experience layer provides a fixed physics-based reference model. In this paper, the reference model is a [[g_g_g_v_diagrams|G-G-G-V]] point-mass envelope distilled from a higher-fidelity two-track model.

The observation layer monitors independent vehicle and controller indicators. Vehicle indicators include front and rear tire slip, slip angle, and combined tire slip. Control indicators include velocity tracking error, lateral acceleration error, lateral deviation, and ESC/TC/ABS intervention levels. Each observer maps its indicator to an incremental update proposal for the local scaling factor.

The anticipation layer predicts expected performance shifts from measurable changes between laps. The implemented predictor uses tire temperature to anticipate grip changes before they fully appear in vehicle response.

The fusion layer, called the explorator, combines observer and predictor proposals into a spatial performance map `theta(s,n)` represented with [[gripmap]]. Conservative fusion uses the most restrictive observer update, allows performance increases mainly near tire-limited operation, and laterally projects learned corrections around the driven line.

The resulting map scales the reference model and feeds an online velocity planner plus a robustified controller stack with MPC, lateral and longitudinal control, countersteer, ESC, ABS, and TC.

## Key Results

In simulation with uniform grip, APEX reaches a 57.93 s lap, while the best globally uniform scaling strategy reaches 58.52 s. APEX also keeps lateral tracking errors much lower than the global scaling run.

In simulation with turn-by-turn varying grip, APEX reaches 58.21 s versus 59.38 s for global scaling. This demonstrates the value of spatial performance-envelope learning when the baseline model is locally wrong.

Adding the tire-temperature predictor improves convergence speed. The observer-only configuration stabilizes in roughly 7-8 laps, while observer plus predictor stabilizes in roughly 4-5 laps with comparable final lap time and tracking error.

In physical validation at the Mercedes-Benz Immendingen handling course on 28 October 2025, APEX runs a 1:59.23 lap in a Mercedes-AMG GT 63 S. George Russell runs 1:57.77 in the same vehicle context, leaving APEX 1.46 s or 1.2% behind. The paper notes that the autonomous car used ESC/TC enabled, while Russell disabled TC and ESC.

At [[abu_dhabi_autonomous_racing_league|A2RL 2025]] on the Yas Marina North layout, TUM Autonomous Motorsport's Hailey sets a 58.183 s best autonomous race lap. Daniil Kvyat's human reference is 57.569 s, leaving Hailey 0.61 s or 1.07% behind. In the AI-vs-AI grand final, Hailey records the fastest autonomous lap and reaches reported maximum accelerations of -29.2 m/s2 longitudinally and 29.5 m/s2 laterally.

Across a six-week A2RL testing and event period, the paper reports 58 sessions and 2000 km driven with APEX continuously enabled, without spins, crashes, or tire-set losses due to flat-spotting.

## Related Work

APEX extends [[gripmap]] from a static spatial constraint framework into an online learned performance envelope. It uses [[g_g_g_v_diagrams]] as a compact reference model and draws its learning principles from [[professional_race_driver_expertise]].

It contrasts with [[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]] and [[champion_level_drone_racing_using_deep_reinforcement_learning]]: those systems achieve champion-level performance with deep RL in simulated or drone-racing settings, while APEX keeps a modular, interpretable, physical-car architecture.

## Notes / Critique

The strongest contribution is practical: APEX shows that a modular stack can learn enough local performance-envelope structure online to get within about 1% of Formula 1 drivers in physical cars. That is a strong post-survey data point for real-world autonomous racing.

The central tradeoff is interpretability versus causal specificity. The learned `theta(s,n)` is interpretable as a local executable-performance correction, but it does not say whether the cause is friction, tire temperature, actuator limits, model error, or controller residuals. This is acceptable for feasibility-aware planning, but weaker for diagnosis and extrapolation to unexplored lines.
