---
tags: [paper]
date: 2026-05-08
task: strategic_rl
venue: "Applied Intelligence"
sources: 1
year: "2025"
doi: "10.1007/s10489-024-06220-4"
url: "https://doi.org/10.1007/s10489-024-06220-4"
topic:
  - reinforcement_learning
  - real_time_strategy_games
tech_backbone: [reinforcement_learning]
tech_representation: []
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
hardware_used: []
simulators_used: []
---

# Deep Reinforcement Learning in Real-Time Strategy Games: A Systematic Literature Review

> Deep Reinforcement Learning in Real-Time Strategy Games: A Systematic Literature Review | Applied Intelligence | Gabriel Caldas Barros and Charles Andrye Galvão Madeira

## Summary

This paper surveys deep reinforcement learning research in real-time strategy games. Its motivation is that RTS environments are unusually difficult for RL because they combine large state and action spaces, partial observability, sparse rewards, and multi-agent decision making.

The review is useful here not because it is a racing paper, but because it maps a neighboring class of strategic environments where learned agents must reason across both tactical and longer-horizon choices.

## Review Focus

The paper structures the literature review around four questions:

- which games are most commonly used as benchmarks,
- which architectures and techniques are applied,
- which simulation environments are adopted,
- and whether the work targets micromanagement or macromanagement.

The review reports that some architectures generalize better across both micro- and macromanagement settings, and that reducing training time and compressing the state representation are recurring practical themes.

## Why It Matters

This paper provides context for strategic multi-agent RL beyond racing. RTS games are a useful comparison class because they stress several of the same decision-making bottlenecks that appear in competitive autonomous systems: opponent modeling, delayed consequences, partial information, and the tension between local action quality and global strategic outcome.

That makes the review a helpful companion to vault entries on racing RL and game-theoretic planning, even though the control modality is different.

## Hardware Used

- No specific demonstration hardware is identified on the current page.


## Related Work

Within this vault, the paper pairs most naturally with [[outracing_champion_gran_turismo_drivers_with_deep_reinforcement_learning]], [[a_competitor_aware_race_management_policy_a_game_theoretical_approach]], and [[out_of_distribution_generalization_with_a_sparc_racing_100_unseen_vehicles_with_a_single_policy]]. Those papers live in racing, but they share the broader strategic-RL concerns of interaction, generalization, and long-horizon consequences.

It also complements the broader agenda in [[welcome_to_the_era_of_experience]], which argues that strong agents will increasingly improve from rich interaction rather than only from static human data.

## Notes / Critique

The strongest contribution is synthesis. For a fast-moving area, a review like this is useful because it shows not just what works, but how researchers divide the problem into tactical and strategic levels.

Its main limitation is that the conclusions are benchmark-driven and domain-specific. RTS insights can inspire autonomous racing work, but they do not solve the continuous-control, vehicle-dynamics, and safety constraints unique to racing.
