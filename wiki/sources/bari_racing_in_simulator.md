---
tags: [source]
date: 2026-05-08
sources: 1
---

# Bari Racing in Simulator Source

> Source: `raw/pdfs/Bari_Racing-in_simulator.pdf`
> Paper: Human Professional Level Driving Agent for Race Car Simulation Environments, AI Open, 2026

## Summary

This paper studies whether a deep reinforcement-learning racing agent can reach human-professional-level performance in a simulator using vehicle-dynamics state inputs rather than camera vision or privileged global game features. The authors compare the learned agent directly against a verified human e-sport champion and ask not only whether lap time is competitive, but whether expert driving behaviors emerge from a simple reward.

For this vault, the paper is useful as a simulation-first, state-based counterpart to the vision-heavy and multi-agent GT papers.

## Method

The agent is trained with PPO from vehicle dynamic signals such as wheel speeds, longitudinal and lateral velocities and accelerations, yaw rate, and track-relative position and heading. It outputs continuous steering and throttle/brake commands and learns from a dense progress-style reward plus terminal penalties and action regularization.

A notable part of the paper is the reward analysis: the authors explicitly connect a reference-time-difference objective to a simpler centerline-progress reward, then augment it with penalties for leaving the track, going backward, damaging the car, or making insufficient progress.

## Evaluation

The evaluation compares the agent with a human simulation-racing champion under nearly identical conditions. The paper reports that the agent reaches lap times close to the human benchmark, while also revealing that some of its fastest behaviors exploit simulator idealizations such as unrealistic actuator sharpness and wheel-locking artifacts.

The paper therefore argues both for success and for caution: the learned policy can become extremely fast, but some of its emergent behaviors are not the same as physically realistic expert driving.

## Notes / Critique

The strongest part of the paper is the qualitative comparison between learned and human driving. It does not stop at lap time; it inspects racing lines, steering traces, braking style, and GG-plot structure.

Its main limitation is exactly what makes it interesting: the agent benefits from simulator artifacts. So the result is a good study of simulator racing competence, but not yet a clean argument for physical-racecar transfer.

## Pages Created From This Source

- [[human_professional_level_driving_agent_for_race_car_simulation_environments]]
- [[vehicle_state_reinforcement_learning]]
