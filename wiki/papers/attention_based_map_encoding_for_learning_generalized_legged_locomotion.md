---
tags: [paper]
date: 2026-05-22
task: robotics
venue: "Science Robotics"
sources: 1
year: "2025"
doi: "10.1126/scirobotics.adv3604"
url: "https://doi.org/10.1126/scirobotics.adv3604"
topic:
  - Highly_dynamic_autonomous_system
  - real_world_robotic_reinforcement_learning
  - quadrupedal_locomotion
  - embodied_autonomous_intelligence
tech_backbone: [reinforcement_learning]
tech_representation: [attention_based_map_encoding, perceptive_locomotion]
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
hardware_used: [quadrupeds, humanoids]
simulators_used: []
---

# Attention-Based Map Encoding for Learning Generalized Legged Locomotion

> Attention-Based Map Encoding for Learning Generalized Legged Locomotion | Science Robotics 2025 | Junzhe He, Chong Zhang, Fabian Jenelten, Ruben Grandia, Moritz Bächer, and Marco Hutter | DOI: 10.1126/scirobotics.adv3604

## Summary

This paper asks how a learning-based legged locomotion controller can preserve robustness while becoming precise enough for sparse, highly structured terrain across more than one robot body.

Its answer is to learn an [[attention_based_map_encoding|attention-based terrain representation]] conditioned on proprioception and train the resulting controller end to end with [[reinforcement_learning]].

## Method

The central idea is [[attention_based_map_encoding]].

Instead of treating the local terrain map as a flat input tensor, the controller learns to attend selectively to terrain regions that matter for future footholds and body motion.

For this vault, the important lesson is representational: terrain perception is not only about having a map, but about learning which parts of that map deserve control authority at a given moment.

The paper positions this as a way to preserve the robustness of learning-based locomotion while recovering some of the precision that model-based planners traditionally maintain on sparse terrain.

## Key Results

According to the paper abstract and publication record, the method is trained and tested on both a 12-DOF quadruped and a 23-DOF humanoid, with real-world evaluations over diverse challenging terrain, including scenarios not seen during training.

The most useful vault takeaway is broader than one benchmark:

**generalized legged locomotion may depend as much on learning the right terrain representation as on learning the control policy itself.**

## Hardware Used

- [[quadrupeds]]
- [[humanoids]]

## Related Work

This paper belongs directly near [[quadrupedal_locomotion]], where it extends the perceptive-locomotion branch from quadruped-specific results toward broader legged generalization.

Compared with [[learning_robust_perceptive_locomotion_for_quadrupedal_robots_in_the_wild]], it puts more emphasis on the terrain encoder itself and on cross-embodiment generalization.

Compared with [[perceptive_locomotion_through_nonlinear_model_predictive_control]], it represents the learning-heavy alternative: rather than turning perception into optimizer constraints, it turns perception into an adaptive internal representation inside a learned policy.

It also belongs near [[real_world_robotic_reinforcement_learning]], because real-world validation on both quadruped and humanoid hardware makes it a stronger embodiment-general result than most single-platform locomotion papers.

## Notes / Critique

The strongest contribution is that the paper reframes generalized locomotion as an attention problem over terrain structure. That is a sharper idea than merely saying “use a map.”

The main caveat is interpretability versus guarantee. Attention can make the learned representation more intelligible than a fully opaque encoder, but it does not automatically provide the feasibility guarantees that a well-structured model-based planner or MPC stack can still offer on extreme terrain.
