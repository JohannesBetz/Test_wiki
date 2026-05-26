---
tags: [source]
date: 2026-05-26
sources: 1
---

# Fu HumanPlus Source

> Source: `raw/pdfs/FU_HumanPlus.pdf`
> Paper: HumanPlus: Humanoid Shadowing and Imitation from Humans, CoRL 2024

## Summary

This paper studies how humanoid robots can learn motion and autonomous skills directly from human data rather than relying only on task-specific robot demonstrations or hand-designed controllers.

For this vault, it matters because it gives the humanoid branch a real `learn from humans at scale` systems story: shadow a human in real time, use that for teleoperated data collection, then imitate the resulting skills autonomously.

## Method

The training backbone combines [[reinforcement_learning]] and supervised imitation.

The paper centers on [[humanplus]], a full-stack system for humanoid shadowing and imitation from humans.

From the public abstract and project-page support, the important pieces are:

- a low-level RL policy trained in simulation from around 40 hours of human motion data,
- real-time humanoid shadowing from a single RGB camera,
- and behavior-cloning-based skill learning from whole-body teleoperation data collected through shadowing.

For this vault, the key point is that HumanPlus treats human data not as a small auxiliary prior, but as the backbone of the humanoid learning pipeline.

## Evaluation

The public record reports real-world shadowing of human body and hand motion and autonomous task performance on a customized 33-DoF 180 cm humanoid across tasks such as standing up after wearing a shoe, unloading warehouse racks, folding a sweatshirt, rearranging objects, typing, and greeting another robot.

The broader takeaway is that humanoid learning from humans becomes more plausible when imitation, teleoperation, and autonomous skill learning are organized as one continuous data pipeline.

## Notes / Critique

The strongest contribution is the pipeline logic. HumanPlus is useful not only as a control result, but as an answer to the question of how humanoids can acquire whole-body skill data without needing massive robot-native demonstration corpora up front.

That makes it a natural complement to:

- [[real_world_humanoid_locomotion_with_reinforcement_learning]], which is more locomotion-centric,
- [[physhsi_towards_a_real_world_generalizable_and_natural_humanoid_scene_interaction_system]], which is more scene-interaction-centric,
- and [[sonic_supersizing_motion_tracking_for_natural_humanoid_whole_body_control]], which is more motion-tracking-centric.

## Pages Created From This Source

- [[humanplus_humanoid_shadowing_and_imitation_from_humans]]
- [[humanplus]]
