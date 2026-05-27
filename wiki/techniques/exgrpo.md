---
tags: [technique]
date: 2026-05-27
sources: 1
---

# ExGRPO

## Definition

ExGRPO is a reasoning-learning technique that uses experience as part of the optimization signal for improving large-model reasoning behavior.

In the vault, the main importance of ExGRPO is conceptual: it treats `experience` as relevant not only for embodied control or agent interaction, but also for symbolic reasoning training.

## Key Approach

[[exgrpo_learning_to_reason_from_experience]] is the current anchor paper for this technique.

The underlying move is to shift reasoning improvement away from pure imitation of static reasoning traces and toward a learning process in which prior outcomes shape future reasoning behavior.

That makes ExGRPO a useful bridge between:

- [[large_language_models]]
- [[reinforcement_learning]]
- and the broader [[era_of_experience]] thesis.

## Relationship to Autonomous Systems

ExGRPO is not a direct autonomous-control technique.

Its value for this vault is upstream. If reasoning systems can learn more effectively from experience, then future autonomy stacks may inherit stronger planning, abstraction, and decision-support capabilities from models that are themselves trained in a more experience-centered way.

Compared with embodied RL methods, ExGRPO is much more abstract and language-centric.

Compared with pure pretraining, it is more explicitly committed to the idea that learning should continue from outcomes and accumulated experience rather than stop at human-authored corpora.

## Representative Papers

- [[exgrpo_learning_to_reason_from_experience]]

## Open Problems

Open problems include:

- whether the method improves genuine reasoning rather than benchmark gaming,
- how robust the learned behavior remains under distribution shift,
- how experience should be represented or prioritized in reasoning domains,
- and whether experience-centered reasoning methods can overcome deeper architectural reasoning limits rather than only compensating for them temporarily.
