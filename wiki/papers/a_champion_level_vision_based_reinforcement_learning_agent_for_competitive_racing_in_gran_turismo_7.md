---
tags: [paper]
date: 2026-05-08
task: autonomous_racing
venue: "IEEE Robotics and Automation Letters"
sources: 1
year: "2025"
topic:
  - autonomous_racing
  - end_to_end_autonomous_racing
  - high_speed_perception
tech_backbone: [reinforcement_learning]
tech_representation: []
tech_generation: [asymmetric_recurrent_actor_critic]
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
simulators_used: [gran_turismo_sport]
---

# A Champion-Level Vision-Based Reinforcement Learning Agent for Competitive Racing in Gran Turismo 7

> A Champion-Level Vision-Based Reinforcement Learning Agent for Competitive Racing in Gran Turismo 7 | IEEE Robotics and Automation Letters | Hojoon Lee, Takuma Seno, Jun Jet Tai, Kaushik Subramanian, Kenta Kawamoto, Peter Stone, and Peter R. Wurman

## Summary

This paper asks whether champion-level competitive racing can be achieved from vision and onboard sensing alone, without the privileged global features used by many leading simulator agents. The answer is yes, at least in Gran Turismo 7: the paper presents a vision-based racing agent that consistently beats the built-in AI field.

That makes it a useful bridge between pure simulator success and more deployment-realistic autonomous racing.

## Method

The key method is [[asymmetric_recurrent_actor_critic]].

The actor receives only egocentric camera input and onboard sensor data, then uses recurrence to retain information about track geometry and opponent positions under occlusion and partial observability. The critic, however, receives global privileged features during training.

This asymmetric setup is paired with additional training choices designed to improve generalization and sample efficiency, including data augmentation and periodic network reinitialization. The reward combines a time-trial-style progress component with a multi-opponent racing reward adapted from prior GT Sophy work.

## Key Results

The paper evaluates the agent in Gran Turismo 7 against 19 built-in AI opponents. The headline result is that the vision-based agent consistently secures first place even when starting from the back of the field.

The paper also reports ablations showing that the asymmetric architecture, recurrent memory module, and regularization strategies each contribute meaningfully to performance.

The broader claim is that this is the first vision-based autonomous racing agent to demonstrate champion-level competitive performance in multi-opponent racing scenarios.

## Related Work

This paper is closely related to [[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]]. Both use GT7 as a high-fidelity racing domain, but GT Sophy depends on global simulator features at inference time, whereas this work constrains the deployed policy to local sensing.

It also connects naturally to [[out_of_distribution_generalization_with_a_sparc_racing_100_unseen_vehicles_with_a_single_policy]], which studies robustness across unseen vehicle contexts, and to [[champion_level_drone_racing_using_deep_reinforcement_learning]], which shows another route to high-speed learned control under stronger sensing realism.

## Notes / Critique

The strongest contribution is the reduction in privileged information at inference. That makes the result more relevant to physical autonomous racing than many prior simulator-only demonstrations.

Its main limitation is that it still depends on simulator training and a privileged critic during learning. So it narrows the realism gap, but it does not close the full sim-to-real problem.
