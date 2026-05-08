---
tags: [source]
date: 2026-05-08
sources: 1
---

# Authier-Carcelen Enhancing Generalization Source

> Source: `raw/pdfs/Carceleen_Enhancing_Generalization.pdf`
> Paper: Enhancing Generalization in Autonomous Driving Through Track-Agnostic Reinforcement Learning, Neural Computing and Applications 2025

## Summary

This paper studies a recurring weakness of reinforcement-learning driving agents: many perform well only when given track-specific information such as centerlines or future curvature samples. The paper asks whether a learned driving policy can generalize across unseen tracks without depending on explicit racetrack geometry.

The proposed answer is a track-agnostic RL framework that removes predefined track features from both the observation design and the reward structure.

## Method

The paper evaluates two PPO-based setups:

- a simplified 2D racing environment with low-dimensional sensor inputs such as Lidar, speed, and acceleration,
- and a higher-fidelity 3D TrackMania setup that combines raw pixels with physics-based features.

The key technical move is a track-independent asymmetry-based reward. Instead of measuring progress relative to a known centerline, the reward uses geometric asymmetry cues from the current observation to estimate whether the vehicle remains centered and well-oriented on the track.

This is paired with multimodal sensor fusion so the policy can learn from both structured signals and visual observations without being handed explicit track geometry.

## Evaluation

The paper reports strong zero-shot generalization to unseen tracks in both settings. In 2D, the baseline model completes all tested alternative tracks and remains close to track-specialized agents in lap time. In 3D, the TrackMania policy completes 5 out of 5 unseen official tracks, though completion rates vary substantially with obstacle richness and track difficulty.

The paper also includes robustness tests under track-scale changes, altered vehicle dynamics, and Gaussian observation noise, reporting high completion rates under moderate perturbations.

## Notes / Critique

The paper is useful because it attacks a different generalization axis from many racing RL papers. Rather than adapting to unseen vehicle dynamics, it tries to remove dependence on track-specific priors in the first place.

The main limitation is evaluation scope. The 3D environment is richer than a toy simulator, but it still differs from physical racing and from dense multi-agent interaction settings. The work is strongest as a zero-shot track-generalization study rather than as a full racing benchmark.

## Pages Created From This Source

- [[enhancing_generalization_in_autonomous_driving_through_track_agnostic_reinforcement_learning]]
- [[track_agnostic_reinforcement_learning]]
