---
tags: [topic]
date: 2026-05-08
sources: 1
---

# Real-Time Strategy Games

## Definition

Real-time strategy games are multi-agent decision environments where agents must act under partial observability, large action spaces, delayed consequences, and simultaneous tactical and strategic demands.

They are widely used as benchmark environments for reinforcement learning because they combine short-horizon control decisions with longer-horizon planning and resource-management consequences.

## Key Framing

[[deep_reinforcement_learning_in_real_time_strategy_games_a_systematic_literature_review]] treats RTS games as a hard testbed for deep RL and organizes the literature around:

- benchmark games and simulators,
- learning architectures and techniques,
- micromanagement tasks,
- and macromanagement tasks.

This framing is useful because it separates local tactical skill from broader strategic reasoning, a distinction that also matters in other competitive domains.

## Relationship to Autonomous Racing

RTS games are not racing, but they are good conceptual neighbors for strategic autonomous racing. Both settings feature competition, imperfect information, long-horizon consequences, and the need to balance immediate tactical moves against broader objectives.

The analogy is not perfect: racing adds continuous control, vehicle dynamics, and physical safety constraints. Still, RTS work is a useful source of ideas for opponent modeling, strategy learning, and hierarchical decision making.

## Representative Papers

- [[deep_reinforcement_learning_in_real_time_strategy_games_a_systematic_literature_review]]

## Open Problems

Open questions include better transfer across maps and opponent styles, improved long-horizon credit assignment, more sample-efficient training, and stronger integration between tactical and strategic reasoning.
