---
tags: [source]
date: 2026-05-08
sources: 1
---

# Barros RL in Strategic Games Source

> Source: `raw/pdfs/Barros_RL-in-strategic_games.pdf`
> Paper: Deep Reinforcement Learning in Real-Time Strategy Games: A Systematic Literature Review, Applied Intelligence, 2025

## Summary

This paper is a systematic literature review of deep reinforcement learning methods applied to real-time strategy games. It is not about autonomous racing directly, but it is relevant as background for multi-agent strategic RL under large state spaces, partial observability, sparse rewards, and mixed micro/macro decision-making.

For this vault, the value of the paper is comparative context. It helps situate racing RL inside a broader family of hard strategic-control environments where agents must learn under complexity, uncertainty, and long-horizon interaction.

## Scope

The review organizes prior work around several questions:

- which real-time strategy games are most commonly used,
- which architectures and RL techniques are applied,
- which simulation environments are favored,
- and whether a paper focuses on micromanagement or macromanagement tasks.

The paper reports that some architectures perform better across both micro- and macromanagement, and that methods for reducing training time and shrinking the state representation often help.

## Relevance

Although the domain differs from autonomous racing, the structural difficulties overlap strongly: partial observability, large action spaces, multi-agent coordination or competition, and long-horizon strategic consequences. That makes RTS work a useful adjacent literature for thinking about race strategy, opponent modeling, and learned tactical behavior.

## Notes / Critique

The strongest aspect is breadth. As a review, it gives a map of architectures, tasks, and benchmark environments rather than advancing one narrow algorithmic claim.

Its main limitation for this vault is indirectness. The findings are informative for strategic RL, but they do not transfer automatically to physical, continuous-control domains like autonomous racing.

## Pages Created From This Source

- [[deep_reinforcement_learning_in_real_time_strategy_games_a_systematic_literature_review]]
- [[real_time_strategy_games]]
