---
tags: [paper]
date: 2026-05-08
task: robotics
venue: "IEEE Transactions on Neural Networks and Learning Systems"
sources: 1
year: "2026"
doi: "10.1109/TNNLS.2026.3656889"
topic:
  - cognitive_navigation
  - embodied_autonomous_intelligence
  - real_world_robotic_reinforcement_learning
tech_backbone: [reinforcement_learning]
tech_representation: []
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
hardware_used: [mobile_robots]
simulators_used: []
---

# A Survey on Learning Motion Planning and Control for Mobile Robots: Toward Embodied Intelligence

> A Survey on Learning Motion Planning and Control for Mobile Robots: Toward Embodied Intelligence | IEEE Transactions on Neural Networks and Learning Systems 2026 | Mengyun Wang, Yifeng Niu, Bo Wang, Wei Zhang, and Chang Wang

## Summary

This paper surveys learning-based approaches to motion planning and control for mobile robots and frames them as part of a larger shift toward embodied intelligence.

The key idea is that planning and control should no longer be viewed only as cleanly separated geometric or optimization subroutines. In embodied systems, they are tightly coupled to sensing, task context, adaptation, and real-world interaction.

## Method

The survey reviews how learning methods are being used to generate motion and control behavior for mobile robots.

Its emphasis includes:

- learning-based motion planning,
- learning-based control,
- [[reinforcement_learning]],
- and imitation-learning-style methods for embodied action.

The embodied-intelligence framing matters here because the paper is not only cataloging algorithms. It is arguing that mobile-robot planning and control are becoming more integrated with perception and interaction, moving autonomy away from rigid modular pipelines toward more adaptive closed-loop behavior.

## Key Results

As a survey, the main result is synthesis rather than a benchmark. The paper's contribution is to show how learning methods are reshaping planning and control for mobile robots and to position that trend within the broader embodied-intelligence agenda.

For this vault, the most useful result is conceptual: it gives a cleaner map of how learning-based control and planning fit between classical robotics and newer embodied-autonomy views.

## Hardware Used

- [[mobile_robots]]


## Related Work

This paper sits naturally next to [[cognitive_navigation_review]], which emphasizes a perception-decision-execution loop for navigation.

It also connects to [[machine_survival_a_historical_perspective_on_embodied_autonomous_intelligence]], but from a more engineering-facing angle: instead of focusing on homeostasis or historical cybernetics, it focuses on the technical evolution of learning-based motion generation in mobile robots.

Compared with [[deep_reinforcement_learning_for_robotics_a_survey_of_real_world_successes]], this survey is broader on planning and control structure but less specifically filtered around physical DRL success cases.

## Notes / Critique

The best part of the paper is that it links concrete robot learning methods to a larger embodied-autonomy story without becoming purely philosophical.

The main limitation is that the embodied framing is still broad. For a racing-focused vault, the paper is most useful as orientation and synthesis, not as a direct answer to high-speed planning and control at the edge of dynamic feasibility.
