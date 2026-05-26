---
tags: [paper]
date: 2026-05-22
task: robotics
venue: "Robotics: Science and Systems (RSS) 2024"
sources: 1
year: "2024"
doi: "10.15607/RSS.2024.XX.059"
url: "https://www.roboticsproceedings.org/rss20/p059.html"
topic:
  - Highly_dynamic_autonomous_system
  - real_world_robotic_reinforcement_learning
  - quadrupedal_locomotion
tech_backbone: [reinforcement_learning]
tech_representation: [agile_but_safe_locomotion]
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
hardware_used: [quadrupeds]
simulators_used: []
---

# Agile But Safe: Learning Collision-Free High-Speed Legged Locomotion

> Agile But Safe: Learning Collision-Free High-Speed Legged Locomotion | Robotics: Science and Systems (RSS) 2024 | Tairan He, Chong Zhang, Wenli Xiao, Guanqi He, Changliu Liu, and Guanya Shi | DOI: 10.15607/RSS.2024.XX.059

## Summary

This paper asks how a legged robot can stay genuinely agile in clutter while avoiding the usual tradeoff where fast learned locomotion becomes brittle or collision-prone once the environment gets tight.

Its answer is `ABS`, a learning-based control framework that couples an aggressive locomotion policy with an explicit recovery mechanism and a learned safety switch.

## Method

The training backbone is [[reinforcement_learning]].

The central idea is [[agile_but_safe_locomotion]].

From the proceedings record and abstract support, the framework contains:

- an agile locomotion policy for fast movement,
- a recovery policy for safer corrective behavior,
- and a learned reach-avoid value network that decides when switching is necessary.

For this vault, the important systems lesson is that safe high-speed locomotion is treated as a policy orchestration problem rather than only as a reward-design problem.

## Key Results

The public record reports collision-free high-speed locomotion in cluttered environments on a physical quadruped with fully onboard sensing and computation.

The most useful vault takeaway is broader than one deployment scene:

**high-dynamic legged competence may need a learned notion of when to stop being aggressive, not only a stronger aggressive policy.**

## Hardware Used

- [[quadrupeds]]

## Related Work

This paper belongs directly near [[rapid_locomotion_via_reinforcement_learning]], but it adds an explicit safety architecture on top of agile learned locomotion rather than only pushing raw performance.

Compared with [[rma_rapid_motor_adaptation_for_legged_robots]], it is less about inferring hidden terrain dynamics and more about recognizing imminent failure risk in cluttered motion.

Compared with [[learning_robust_perceptive_locomotion_for_quadrupedal_robots_in_the_wild]], it is less about terrain-perception trust and more about collision-aware policy switching under tight spatial constraints.

It also belongs near [[Highly_dynamic_autonomous_system]], because it sharpens a question that reaches well beyond quadrupeds: when a system is near the limit, how should it decide that preserving viability matters more than preserving maximum speed?

## Notes / Critique

The strongest contribution is architectural. The paper refuses the usual false choice between one aggressive policy and one conservative policy by learning when to move between them.

The main caveat is that the current ingest is based on the RSS proceedings record and public abstract support rather than a clean full-text parse of the local PDF. So I’ve written it as a careful method-level anchor in the safety-aware quadruped branch rather than pretending we have every implementation detail nailed down.
