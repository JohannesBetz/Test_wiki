---
tags: [source]
date: 2026-05-07
sources: 1
---

# Orchestrating Cognitive Skill Distillation Source

> Source: `raw/pdfs/Hou_Orchestrating_Cognitive Skill_Distillation.pdf`

## Summary

This manuscript introduces [[csdal|Cognitive Skill Distillation and Alternating Learning (CSDAL)]], an autonomous-racing policy framework that integrates expert driving demonstrations, knowledge distillation, and curriculum learning into a Soft Actor-Critic training loop.

The paper targets trajectory planning and motion control for [[autonomous_vehicle_racing]], where an agent must improve lap time while respecting vehicle handling limits and safety constraints. Its central idea is to make the RL agent learn from expert laps early, preserve important skill memories, and then progressively expand the task difficulty so the learned policy can surpass the expert data.

## Method

CSDAL combines two modules:

- [[hippocampal_inspired_skill_consolidation_and_distillation|HISCD]]: selects critical memory epochs based on skill improvement, periodically reviews stored memory nodes, and uses a CNN-LSTM temporal distillation loss to guide the SAC student network toward expert teacher features.
- [[alternating_phases_curriculum_learning|APCL]]: alternates reverse curriculum learning from expert-proximal track segments with forward curriculum learning that broadens initial state distributions using noise estimated from non-optimal expert trajectories.

The base RL algorithm is [[soft_actor_critic]]. The action space modifies the expert reference path and velocity profile by outputting commanded lateral displacement and residual tangential velocity. A lower-level NMPC planner tracks the CSDAL-generated path and velocity commands.

## Evaluation

The authors evaluate CSDAL in rFactor 2 on three tracks:

- Atlanta 2017: 4039 m, 10 segments, 5 curves.
- Atlanta MP: 2941 m, 14 segments, 8 curves.
- Mugello Circuit: 5204 m, 17 segments, 9 curves.

Baselines are naive SAC, APCL-SAC, HISCD-SAC, and expert demonstrations. On Atlanta MP, lap times are expert 81.7 s, APCL-SAC 79.6 s, HISCD-SAC 77.9 s, and CSDAL 75.7 s. Similar total-lap improvements are reported on Atlanta 2017 and Mugello.

## Notes / Critique

The paper is useful for the wiki because it gives a concrete learning-from-expert framework for autonomous racing that sits between imitation learning, knowledge distillation, curriculum learning, and RL control. It also directly addresses catastrophic forgetting and sparse long-horizon rewards.

Important caveat: the file is a manuscript draft with an Information Sciences submission marker, so claims should be treated as provisional until publication status is verified.

## Pages Created From This Source

- [[learn_consolidate_dominate_orchestrating_cognitive_skill_distillation_and_alternating_learning_for_autonomous_racing]]
- [[csdal]]
- [[hippocampal_inspired_skill_consolidation_and_distillation]]
- [[alternating_phases_curriculum_learning]]
- [[curriculum_learning]]
- [[knowledge_distillation]]
- [[rfactor_2]]
