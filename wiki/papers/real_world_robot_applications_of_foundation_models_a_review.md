---
tags: [paper]
date: 2026-05-13
task: ai_systems
venue: "Advanced Robotics 2024"
sources: 1
year: "2024"
doi: "10.1080/01691864.2024.2408593"
url: "https://doi.org/10.1080/01691864.2024.2408593"
topic:
  - foundation_models_for_intelligent_decision_making
  - embodied_autonomous_intelligence
  - real_world_robotic_foundation_models
tech_backbone: []
tech_representation: []
tech_generation: [foundation_models_for_intelligent_decision_making]
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
hardware_used: [multiple_robot_embodiments]
simulators_used: []
---

# Real-world robot applications of foundation models: a review

> Real-world robot applications of foundation models: a review | Advanced Robotics 2024 | Kento Kawaharazuka, Tatsuya Matsushima, Andrew Gambardella, Jiaxian Guo, Chris Paxton, and Andy Zeng

## Summary

This paper reviews how foundation models are being applied to physical robots in real-world scenarios.

Its main value for this vault is that it shifts the discussion from abstract foundation-model promise to embodied deployment reality: what these models can help with on real robots, and where physical-world constraints still dominate.

## Method

The paper is a review of real-world robotic applications of foundation models, organized around physical deployment rather than only benchmark performance.

That focus matters. In robotics, the question is not whether a model can produce plausible outputs in isolation, but whether it can support sensing, planning, manipulation, or action selection under embodiment, latency, safety, and reliability constraints.

The paper therefore functions as a map of where foundation models are beginning to contribute to robotics and where they still require significant scaffolding from classical systems engineering.

## Key Results

Because this is a review, the key result is a synthesis: foundation models are becoming useful in real robotics, but their success is uneven and strongly mediated by system design.

For this vault, the central takeaway is that real-world robotic progress does not come from dropping a giant model into the loop by itself. It comes from careful integration with perception pipelines, planners, controllers, safety logic, and embodied task structure.

## Hardware Used

- [[multiple_robot_embodiments]]


## Related Work

This paper belongs directly near [[foundation_models_for_intelligent_decision_making]], but it is more concrete and more honest about deployment constraints than that broader decision-making review.

It also fits naturally with [[embodied_autonomous_intelligence]], because it highlights the persistent mismatch between broad pretrained priors and the grounded sensorimotor demands of physical robots.

Compared with [[a_survey_on_learning_motion_planning_and_control_for_mobile_robots_toward_embodied_intelligence]], this paper is less about the full learning-for-control landscape and more specifically about where foundation models slot into real embodied systems.

Compared with [[racevla_vla_based_racing_drone_navigation_with_human_like_behaviour]], this review provides the broader context for why VLA-style results are exciting but also fragile: robotics deployment is where latency, grounding, and control precision stop being side issues.

## Notes / Critique

The strongest contribution is its calibration value. It helps prevent the vault's foundation-model branch from drifting too far into abstract capability claims without physical-world evidence.

For embodied autonomy, that is important. Real robots do not care whether a model sounds general; they care whether it can act reliably under tight sensorimotor constraints.
