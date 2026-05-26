---
tags: [paper]
date: 2026-05-24
task: robotics
venue: "arXiv"
sources: 1
year: "2023"
doi: "10.48550/arXiv.2305.14654"
url: "https://doi.org/10.48550/arXiv.2305.14654"
topic:
  - Highly_dynamic_autonomous_system
  - quadrupedal_locomotion
tech_backbone: [reinforcement_learning]
tech_representation: []
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: [barkour]
models_used: []
hardware_used: [quadrupeds]
simulators_used: []
---

# Barkour: Benchmarking Animal-level Agility with Quadruped Robots

> Barkour: Benchmarking Animal-level Agility with Quadruped Robots | arXiv 2023 | Ken Caluwaerts, Atil Iscen, J. Chase Kew, Wenhao Yu, Tingnan Zhang, Daniel Freeman, Kuang-Huei Lee, Lisa Lee, Stefano Saliceti, Vincent Zhuang, Nathan Batchelor, Steven Bohez, Federico Casarini, Jose Enrique Chen, Omar Cortes, Erwin Coumans, Adil Dostmohamed, Gabriel Dulac-Arnold, Alejandro Escontrela, Erik Frey, Roland Hafner, Deepali Jain, Bauyrjan Jyenis, Yuheng Kuang, Edward Lee, Linda Luu, Ofir Nachum, Ken Oslund, Jason Powell, Diego Reyes, Francesco Romano, Fereshteh Sadeghi, Ron Sloat, Baruch Tabanpour, Daniel Zheng, Michael Neunert, Raia Hadsell, Nicolas Heess, Francesco Nori, Jeff Seto, Carolina Parada, Vikas Sindhwani, Vincent Vanhoucke, and Jie Tan | DOI: 10.48550/arXiv.2305.14654

## Summary

This paper asks how quadruped agility should be measured in a way that reflects more than one narrow gait or one handpicked terrain demo.

Its answer is [[barkour]], an obstacle-course benchmark inspired by dog agility competitions, together with two baseline solution families that show how agile locomotion can be evaluated under a common scoring system.

## Method

The central contribution is the [[barkour]] benchmark itself.

The course combines diverse obstacle types inside a compact area and uses a time-based score with penalties, which encourages systems that are not only fast but also versatile and controllable.

To establish baselines, the paper reports:

- specialist locomotion skills trained with on-policy [[reinforcement_learning]] and combined with a higher-level navigation controller,
- and a distilled Transformer-based generalist locomotion policy called `Locomotion-Transformer`.

For this vault, the important systems lesson is that agility research needs shared evaluation structure, not only isolated demonstrations.

## Key Results

The public record reports that a custom-built quadruped can complete the course at roughly half the speed of a dog using the presented learning-based methods.

The most useful vault takeaway is broader than the headline number:

**quadruped agility becomes much easier to compare across methods once speed, versatility, obstacle handling, and controllability are all embedded into one benchmark rather than scattered across unrelated demos.**

## Hardware Used

- [[quadrupeds]]

## Related Work

This paper belongs near [[quadrupedal_locomotion]], but as a benchmark anchor rather than only as another controller paper.

Compared with [[rapid_locomotion_via_reinforcement_learning]], it is less about maximizing one locomotion pipeline and more about defining what agility should mean across pipelines.

Compared with [[robot_parkour_learning]], it is less about one end-to-end parkour policy and more about a reusable evaluation scaffold for many future policies.

It also belongs near [[Highly_dynamic_autonomous_system]], because one of the hardest problems in high-dynamic robotics is not only building fast systems but agreeing on how their agility should be measured.

## Notes / Critique

The strongest contribution is benchmark design. The paper gives the quadruped branch a cleaner language for talking about animal-level agility.

The main caveat is that benchmarks can also narrow the field if the obstacle design or scoring assumptions become too influential. Barkour is powerful as a shared target, but it should not quietly become the only definition of agile legged competence.
