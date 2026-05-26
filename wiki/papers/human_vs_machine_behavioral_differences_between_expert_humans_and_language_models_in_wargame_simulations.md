---
tags: [paper]
date: 2026-05-08
task: strategic_decision_making
venue: "AAAI/ACM Conference on AI, Ethics, and Society"
sources: 1
year: "2024"
topic:
  - real_time_strategy_games
  - foundation_models_for_intelligent_decision_making
tech_backbone: []
tech_representation: []
tech_generation: [ai_wargaming]
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
hardware_used: []
simulators_used: []
---

# Human vs. Machine: Behavioral Differences between Expert Humans and Language Models in Wargame Simulations

> Human vs. Machine: Behavioral Differences between Expert Humans and Language Models in Wargame Simulations | AIES 2024 | Max Lamparth, Anthony Corso, Jacob Ganz, Oriana Skylar Mastro, Jacquelyn Schneider, and Harold Trinkunas

## Summary

This paper studies how large language models behave in high-stakes strategic conflict simulations compared with expert humans. The motivating concern is that LLMs might be used for military recommendation, planning support, or even more autonomous strategic decision roles before their behavioral differences from human experts are properly understood.

The paper therefore treats wargaming as a testbed for whether language models merely sound strategic or whether they actually behave in ways similar to human expert teams.

## Method

The authors build a fictional US-China crisis wargame with two moves, treatment variations, and a structured action set. Human data come from 107 national security experts organized into teams.

The model comparison uses GPT-3.5 and GPT-4 to simulate teams under different prompting styles. Some variants ask the model to output a team decision directly, while others first ask it to simulate internal dialogue among team members.

The analysis compares:

- overall action overlap with humans,
- escalation tendencies,
- response sensitivity to treatment changes,
- consistency across game moves,
- and the quality of simulated internal team discussion.

## Key Results

The paper finds meaningful high-level overlap between LLM and human responses, but also systematic differences that matter in a strategic setting.

The major reported findings are:

- LLM-simulated teams can be more aggressive than human expert teams,
- model behavior changes substantially with prompting and model choice,
- simulated internal dialogue tends to show shallow debate and unrealistic harmony,
- and LLMs do not meaningfully reflect strong human player-trait differences such as extreme pacifism or aggressiveness.

The main practical conclusion is caution: even when a model appears broadly aligned with expert choices at a coarse level, its finer strategic tendencies may still be badly mismatched for real high-stakes use.

## Hardware Used

- No specific demonstration hardware is identified on the current page.


## Related Work

For this vault, the paper sits closest to [[real_time_strategy_games]] and [[foundation_models_for_intelligent_decision_making]]. It is not about robotics or racing, but it is relevant to strategic decision-making under uncertainty, partial information, and long-horizon consequences.

Compared with the broad survey [[foundation_models_and_intelligent_decision_making_progress_challenges_and_perspectives]], this paper is much narrower and more empirical. It focuses on one especially sensitive use case and shows that apparent general competence does not guarantee acceptable strategic behavior.

It also complements [[deep_reinforcement_learning_in_real_time_strategy_games_a_systematic_literature_review]] by shifting from RL game competence toward LLM-based strategic judgment and behavioral alignment.

## Notes / Critique

The best part of the paper is the direct human-expert comparison. That makes the claims about behavioral mismatch much more credible than generic speculation about LLMs in warfare.

The main limitation is ecological distance. Even carefully designed wargames are still proxies for real strategic choice, so the results are best read as a warning sign rather than a complete map of model behavior under genuine geopolitical stress.
