---
tags: [paper]
date: 2026-05-07
task: autonomous_racing
venue: "Information Sciences 2026 manuscript"
sources: 1
year: "2026"
topic:
  - autonomous_racing
  - trajectory_planning
  - motion_control
  - reinforcement_learning
  - curriculum_learning
  - knowledge_distillation
tech_backbone: [cnn]
tech_representation: []
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: [csdal]
hardware_used: [cars_and_race_cars]
simulators_used: [rfactor_2]
---

# Learn, Consolidate, Dominate (2026)

> Learn, Consolidate, Dominate: Orchestrating Cognitive Skill Distillation and Alternating Learning for Autonomous Racing | Information Sciences manuscript draft | Hou et al.

## Summary

This paper proposes [[csdal]], a learning framework for autonomous racing trajectory planning and motion control. CSDAL augments [[soft_actor_critic]] with expert-skill distillation and alternating curriculum learning so an agent can learn efficiently from expert laps, retain useful skills, and then improve beyond the expert reference.

## Method

CSDAL has two main modules.

[[hippocampal_inspired_skill_consolidation_and_distillation|HISCD]] is inspired by hippocampal memory consolidation and the Ebbinghaus forgetting curve. A teacher network is trained from expert driving demonstrations collected in [[rfactor_2]]. The SAC student network periodically stores memory nodes at epochs with high skill improvement, reviews recent memory nodes, and uses a CNN-LSTM model to predict knowledge increments. A temporal distillation loss compares predicted feature increments with teacher-student feature differences, guiding the student early in training. The distillation weight decays to zero so later training can optimize task return more freely.

[[alternating_phases_curriculum_learning|APCL]] is inspired by the zone of proximal development. It divides the track into corner/straight segments and alternates:

- Reverse curriculum: the guide policy handles earlier expert segments while the RL exploration policy takes over later segments, then the handoff point moves backward toward the start.
- Forward curriculum: the initial state distribution for each phase is broadened using noise estimated from non-optimal expert trajectories.

The state is represented in Serret-Frenet coordinates around the expert reference line and includes path displacement, sideslip, speed, yaw, yaw rate, tangential velocity, accelerations, curriculum index, and mode flags. The action modifies the expert path and velocity by commanding lateral displacement and residual tangential velocity. A lower-level NMPC tracker converts these commands into vehicle controls.

## Key Results

The authors evaluate on Atlanta 2017, Atlanta MP, and Mugello Circuit. CSDAL is compared against naive SAC, APCL-SAC, HISCD-SAC, and expert data.

On Atlanta MP, reported total lap times are:

- Expert data: 81.7 s.
- APCL-SAC: 79.6 s.
- HISCD-SAC: 77.9 s.
- CSDAL: 75.7 s.

On Atlanta 2017, CSDAL reduces the expert lap time from 90.4 s to 84.1 s. On Mugello, CSDAL reduces the expert lap time from 123.3 s to 114.0 s. The paper also reports that CSDAL trajectories use the vehicle's acceleration envelope more aggressively, especially in corner segments, implying higher adhesion utilization and shorter lap times.

## Datasets Used

Expert data are collected from driver-in-the-loop operation in [[rfactor_2]]. For each track, the top 10 shortest expert laps are used to train the teacher model.

## Hardware Used

- [[cars_and_race_cars]]


## Related Work

This paper builds on the autonomous-racing RL line summarized by [[autonomous_vehicles_on_the_edge]] and relates to [[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]] through model-free RL for racing. It differs from [[gt_sophy]] by focusing on trajectory planning and motion control around expert reference trajectories, rather than integrated multi-agent race tactics.

The curriculum-learning aspect complements [[mixed_scenario_training]]: both aim to expose the agent to decisive states, but APCL structures exposure by track phase and expert-proximal states rather than by hand-designed tactical scenarios.

## Notes / Critique

The main contribution is the combination of expert distillation, memory review, and alternating curriculum inside an SAC-based autonomous-racing policy. The strongest claim is improved lap time over expert data and module ablations on multiple track maps.

The main limitation is reliance on expert demonstrations. The authors also state this directly: broader generalization to new environments may require accumulating richer map and expert-knowledge experience so the algorithm can eventually reduce prior expert guidance.

Because the supplied PDF is a manuscript draft, publication details and final peer-reviewed claims should be verified before treating this as settled evidence.
