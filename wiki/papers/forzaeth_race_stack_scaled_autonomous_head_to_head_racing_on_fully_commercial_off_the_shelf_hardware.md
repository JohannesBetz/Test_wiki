---
tags: [paper]
date: 2026-05-13
task: autonomous_racing
venue: "Journal of Field Robotics 2025"
sources: 1
year: "2025"
doi: "10.1002/rob.22429"
topic:
  - autonomous_racing
  - autonomous_racing_platforms
  - autonomous_racing_control
  - autonomous_racing_planning
tech_backbone: []
tech_representation: []
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: [f1tenth]
models_used: [forzaeth_race_stack]
hardware_used: [cars_and_race_cars]
simulators_used: []
---

# ForzaETH Race Stack—Scaled Autonomous Head-to-Head Racing on Fully Commercial Off-the-Shelf Hardware

> ForzaETH Race Stack—Scaled Autonomous Head-to-Head Racing on Fully Commercial Off-the-Shelf Hardware | Journal of Field Robotics 2025 | Nicolas Baumann, Edoardo Ghignone, Jonas Kuhne, Niklas Bastuck, Jonathan Becker, Nadine Imholz, Tobias Kranzlin, Tian Yi Lim, Michael Lotscher, Luca Schwarzenbach, Luca Tognoni, Christian Vogt, Andrea Carron, and Michele Magno

## Summary

This paper presents the ForzaETH Race Stack, a modular software stack for scaled autonomous head-to-head racing on 1:10 vehicles built from fully commercial off-the-shelf hardware.

The central problem it addresses is reproducibility. Many autonomous-racing systems are powerful but difficult to replicate because they depend on custom hardware, hidden integration effort, or time-trial-only assumptions. ForzaETH instead aims to be competitive, modular, and broadly adoptable.

## Method

The system is designed for scaled autonomous racing, especially the [[f1tenth]] ecosystem and head-to-head competition settings.

Its main architectural emphasis is full-stack integration:

- robotic perception,
- state estimation,
- path planning,
- motion control,
- and practical operational workflows for racing deployment.

The paper highlights modularity and ease of use as core design principles, which is important because the goal is not only performance but also faster onboarding and adaptation to different tracks and conditions.

## Key Results

The paper reports that the stack has demonstrated robustness and strong field performance, including multiple wins in the official F1TENTH international competition.

It also emphasizes scale of operation, reporting reliable deployment on tracks up to roughly 150 m, which is unusually large for this class of scaled autonomous-racing platform.

For this vault, the most important result is that full head-to-head racing can be made accessible without specialized custom hardware, which lowers the barrier for repeatable research on multi-agent autonomous racing.

## Hardware Used

- [[cars_and_race_cars]]


## Related Work

This paper belongs naturally near [[autonomous_racing_platforms]] and [[f1tenth]]. It gives the scaled-platform side of the field a concrete, modern full-stack reference similar in spirit to how larger racecar programs function at full scale.

It also complements [[benchmarking_of_a_software_stack_for_autonomous_racing_against_a_professional_human]], though from a different scale and goal. The benchmarking paper compares a full stack against a professional driver, while this paper focuses more on reproducible system architecture and head-to-head competition readiness.

Compared with more focused method papers such as [[spatially_aware_adaptive_trajectory_optimization_with_controller_guided_feedback_for_autonomous_racing]], this paper is broader and more infrastructural: it treats the whole racing stack as the main contribution.

## Notes / Critique

The strongest contribution is accessibility without trivialization. The paper shows that a commercial-off-the-shelf scaled platform can still be serious enough for competitive head-to-head racing research.

The main limitation is transfer. A strong scaled stack does not automatically answer how the same architecture should change for full-scale racecars, where sensing range, actuation, safety envelopes, and tire dynamics become much harsher.
