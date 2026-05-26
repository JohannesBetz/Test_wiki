---
tags: [paper]
date: 2026-05-22
task: robotics
venue: "Robotics: Science and Systems (RSS) 2025"
sources: 1
year: "2025"
doi: "10.15607/RSS.2025.XXI.068"
url: "https://www.roboticsproceedings.org/rss21/p068.html"
topic:
  - Highly_dynamic_autonomous_system
  - embodied_autonomous_intelligence
  - real_world_robotic_reinforcement_learning
tech_backbone: [reinforcement_learning]
tech_representation: [perceptive_locomotion]
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
hardware_used: [humanoids]
simulators_used: []
---

# BeamDojo: Learning Agile Humanoid Locomotion on Sparse Footholds

> BeamDojo: Learning Agile Humanoid Locomotion on Sparse Footholds | Robotics: Science and Systems (RSS) 2025 | Huayi Wang, Zirui Wang, Junli Ren, Qingwei Ben, Tao Huang, Weinan Zhang, and Jiangmiao Pang | DOI: 10.15607/RSS.2025.XXI.068

## Summary

This paper asks how a humanoid can traverse sparse footholds reliably enough that agile locomotion does not collapse as soon as the terrain stops being dense and forgiving.

Its answer is BeamDojo, a learning framework that couples efficient RL training with terrain-aware deployment perception for precise foothold placement on a physical humanoid.

## Method

The training backbone is [[reinforcement_learning]].

From the paper title, proceedings record, and abstract support, the system uses a two-stage RL pipeline that balances ordinary locomotion shaping with the much sparser objective of landing valid footholds.

On the deployment side, the system uses an onboard LiDAR-based elevation map, which makes this paper a humanoid-side member of the [[perceptive_locomotion]] branch rather than only another locomotion benchmark.

For this vault, the central systems lesson is that sparse-terrain humanoid agility depends on two things at once:

- learning a controller that can remain aggressive enough to move efficiently,
- and giving that controller terrain information in a form that supports precise foot placement in the real world.

## Key Results

The public record reports both simulation and real-world experiments.

The main high-level result is that BeamDojo enables agile humanoid locomotion on sparse footholds with precise foot placement and strong disturbance robustness.

The most useful vault takeaway is broader than one terrain course:

**humanoid high-dynamic behavior can be extended from flat-ground locomotion and parkour demos toward foothold-constrained terrain when learning efficiency and deployment perception are co-designed.**

## Hardware Used

- [[humanoids]]

## Related Work

This paper belongs near [[learning_robust_perceptive_locomotion_for_quadrupedal_robots_in_the_wild]], but it shifts the perceptive-locomotion story from quadrupeds to humanoids and from general rough terrain to explicitly sparse footholds.

Compared with [[perceptive_locomotion_through_nonlinear_model_predictive_control]], BeamDojo appears much more learning-centric and much less optimizer-centric, even though both papers revolve around terrain-aware foothold reasoning.

Compared with [[humanoid_parkour_learning]], this paper looks narrower in maneuver diversity but sharper in terrain precision and foothold validity.

It also belongs naturally near [[Highly_dynamic_autonomous_system]], because sparse footholds turn locomotion into a real-time precision problem rather than only a speed or robustness problem.

## Notes / Critique

The strongest contribution is the way the paper tightens the connection between humanoid agility and perceptive terrain reasoning. It makes the humanoid branch feel less like fast motion on broad terrain and more like a real test of exact embodied placement under pressure.

The main caveat is that the local PDF text layer is weak, so this ingest is anchored to the proceedings record, DOI, and public abstract support rather than a full clean parse of every experimental detail. I’ve written it as a careful high-level placement rather than pretending we have every implementation nuance pinned down.
