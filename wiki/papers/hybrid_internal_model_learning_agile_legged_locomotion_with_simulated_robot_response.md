---
tags: [paper]
date: 2026-05-26
task: robotics
venue: "International Conference on Learning Representations (ICLR) 2024"
sources: 1
year: "2024"
doi: "10.48550/arXiv.2312.11460"
url: "https://doi.org/10.48550/arXiv.2312.11460"
topic:
  - Highly_dynamic_autonomous_system
  - real_world_robotic_reinforcement_learning
  - quadrupedal_locomotion
tech_backbone: [reinforcement_learning]
tech_representation: [hybrid_internal_model, sim_to_real_transfer]
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

# Hybrid Internal Model: Learning Agile Legged Locomotion with Simulated Robot Response

> Hybrid Internal Model: Learning Agile Legged Locomotion with Simulated Robot Response | International Conference on Learning Representations (ICLR) 2024 | Junfeng Long, Zirui Wang, Quanyi Li, Jiawei Gao, Liu Cao, and Jiangmiao Pang | DOI: 10.48550/arXiv.2312.11460

## Summary

This paper asks whether a quadruped can achieve robust agile locomotion without explicitly modeling the terrain or using rich exteroceptive sensing.

Its answer is `HIM`, a `Hybrid Internal Model` that uses the robot's own historical internal states to estimate explicit velocity and an implicit disturbance-relevant response. The result is a locomotion policy that tries to infer environmental disturbance from the body's behavior rather than from a terrain map.

## Method

The central idea is [[hybrid_internal_model]].

The architecture contains:

- a policy network for locomotion control,
- and a hybrid internal model that predicts explicit velocity together with an implicit latent response linked to stability and system dynamics.

According to the public project description, the policy uses only proprioceptive inputs and an IMU. Instead of explicitly estimating terrain properties such as elevation, friction, or restitution, the model treats those factors as disturbances and learns an embedding that helps the policy infer them from the robot's own response.

The embedding is optimized with contrastive learning, which is important for this vault because it shows a different route to robustness than the more common privileged-terrain-teacher or explicit-map strategies in quadruped locomotion.

## Key Results

The public record reports strong agility over challenging terrain in both simulation and real-world experiments on Unitree quadruped robots, with additional simulator evidence on Cassie as a second embodiment.

For this vault, the key result is broader than one traversal demo:

**agile legged locomotion may be improved not only by richer terrain observation, but by learning a better internal response model of the robot itself.**

## Hardware Used

- [[quadrupeds]]

## Related Work

This paper belongs directly near [[quadrupedal_locomotion]], where it adds a disturbance-inference-centered complement to the current quadruped entries.

Compared with [[rma_rapid_motor_adaptation_for_legged_robots]], this paper is less about a separate adaptation module that infers latent terrain and dynamics changes online and more about learning an internal response representation that supports robust control under minimal sensing.

Compared with [[learning_robust_perceptive_locomotion_for_quadrupedal_robots_in_the_wild]], it represents almost the opposite philosophy: instead of leaning harder on terrain perception, it tries to recover robustness from internal response modeling with only proprioception and IMU sensing.

It also belongs near [[real_world_robotic_reinforcement_learning]] and [[sim_to_real_transfer]], because it is another physically serious case where the deployment result depends on architectural structure as much as on the RL objective.

## Notes / Critique

The strongest contribution is conceptual compression. The paper suggests that part of what other systems explicitly sense from the world may instead be recoverable from the body's own response, if the representation is learned well enough.

That makes it a useful counterpoint inside the quadruped branch:

- some papers push richer perception,
- some push online latent adaptation,
- and this one pushes internal response modeling as the route to robust agility.
