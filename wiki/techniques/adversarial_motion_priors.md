---
tags: [technique]
date: 2026-05-26
sources: 1
---

# Adversarial Motion Priors

## Definition

Adversarial motion priors are learned motion-structure constraints used during policy training so a locomotion controller is optimized not only for external task reward, but also for whether its behavior matches a learned notion of desirable motion.

## Key Approaches

In [[learning_robust_and_agile_legged_locomotion_using_adversarial_motion_priors]], this idea is used to shape legged locomotion learning toward more robust and agile behavior through an adversarially learned motion prior.

In [[physhsi_towards_a_real_world_generalizable_and_natural_humanoid_scene_interaction_system]], an AMP-style motion-prior backbone reappears on the humanoid side as part of a broader real-world scene-interaction stack.

For this vault, the main point is that locomotion learning can be guided by a learned prior over motion quality rather than only by hand-designed reward shaping, explicit controller structure, or terrain sensing.

## Representative Papers

- [[learning_robust_and_agile_legged_locomotion_using_adversarial_motion_priors]]
- [[physhsi_towards_a_real_world_generalizable_and_natural_humanoid_scene_interaction_system]]

## Open Problems

The main open question is what exactly the prior is teaching. A motion prior can stabilize learning and improve style or coordination, but it may also bake in hidden assumptions about what counts as desirable behavior.

Another important question for the vault is how these priors compare with other structure sources such as terrain perception, explicit optimization, latent adaptation, or safety switching when the robot faces genuinely novel terrain and disturbances.
