---
tags: [paper]
date: 2026-05-22
task: robotics
venue: "arXiv"
sources: 1
year: "2022"
doi: "10.48550/arXiv.2205.02824"
url: "https://doi.org/10.48550/arXiv.2205.02824"
topic:
  - Highly_dynamic_autonomous_system
  - real_world_robotic_reinforcement_learning
  - quadrupedal_locomotion
tech_backbone: [reinforcement_learning]
tech_representation: [curriculum_learning, sim_to_real_transfer]
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

# Rapid Locomotion via Reinforcement Learning

> Rapid Locomotion via Reinforcement Learning | arXiv 2022 | Gabriel B. Margolis, Ge Yang, Kartik Paigwar, Tao Chen, and Pulkit Agrawal | DOI: 10.48550/arXiv.2205.02824

## Summary

This paper asks whether a quadrupedal robot can achieve genuinely rapid, agile real-world locomotion from a policy learned through reinforcement learning rather than from a largely hand-designed controller.

Its answer is yes, with an end-to-end neural controller for the MIT Mini Cheetah that is trained in simulation and transferred to physical terrain.

## Method

The controller is trained with [[reinforcement_learning]] and deployed as a fast locomotion policy rather than as a classical gait scheduler or trajectory-tracking stack.

The two method details that matter most for this vault are:

- an adaptive [[curriculum_learning|curriculum]] over commanded velocities, which helps the policy acquire more aggressive motion capabilities progressively,
- and an online [[sim_to_real_transfer|system-identification-driven sim-to-real strategy]], which helps reduce the mismatch between simulator dynamics and real deployment.

That combination makes the paper a useful example of how experience-driven learning in embodied robotics is usually strongest when the learning process is structured rather than left fully naive.

## Key Results

The paper reports high-speed locomotion and turning on natural outdoor terrain, with the Mini Cheetah sustaining speeds up to about `3.9 m/s`.

For the vault, the most important result is broader than the speed number:

**rapid learned quadruped locomotion is a real physical success case, not just a simulator promise.**

That gives the legged-robotics branch stronger footing inside the wiki's overall argument that extreme embodied competence can be learned from experience.

## Hardware Used

- [[quadrupeds]]


## Related Work

This paper belongs directly near [[real_world_robotic_reinforcement_learning]], since it is one of the cleaner examples that physically deployed RL can deliver serious embodied capability in domains where timing, disturbances, and terrain matter.

It also belongs near [[quadrupedal_locomotion]], where it complements [[high_speed_control_and_navigation_for_quadrupedal_robots_on_complex_and_discrete_terrain]]. The Margolis paper is more explicitly about rapid locomotion through learned control, while the Kim paper pushes more toward tightly coupled high-speed control and navigation on complex discrete terrain.

Compared with [[champion_level_drone_racing_using_deep_reinforcement_learning]], the embodiment changes but the systems lesson rhymes: high performance comes not from RL alone, but from RL plus a disciplined sim-to-real pipeline and a carefully structured training process.

The paper also reinforces the survey-level point in [[deep_reinforcement_learning_for_robotics_a_survey_of_real_world_successes]] that quadruped locomotion is one of the most mature real-world DRL success areas.

## Notes / Critique

The strongest contribution is that it turns fast quadruped locomotion into a convincing experience-driven embodied result instead of an aspirational benchmark.

The main caveat is generality. Strong locomotion on the Mini Cheetah does not automatically solve broader extreme-environment autonomy questions like terrain-semantic reasoning, richer navigation objectives, or long-horizon task adaptation. Still, as a demonstration of what structured RL can do on real high-dynamic hardware, it is a very important anchor.
