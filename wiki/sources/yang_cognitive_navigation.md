---
tags: [source]
date: 2026-05-07
sources: 1
---

# Yang Cognitive Navigation Source

> Source: `raw/pdfs/Yang_Cognitive_navigation.pdf`
> Paper: Cognitive navigation, Science China Information Sciences, 2026

## Summary

This paper is a broad review and position piece on [[cognitive_navigation]]. It argues that modern navigation systems are moving beyond classical geometric route-following toward a more general cognitive framework in which agents perceive the world, make task-aware decisions, and execute actions in a closed loop.

The paper is not specific to autonomous racing, but it is useful as a high-level conceptual frame for the whole autonomy stack. Its core lens is that navigation should be understood as a tightly coupled perception-decision-execution system rather than as isolated modules.

## Method / Framing

The paper defines cognitive navigation as a navigation paradigm that integrates:

- Cognitive perception of the environment and the agent's internal state.
- Cognitive decision making for safe, immediate, and goal-directed task planning.
- Cognitive execution that turns task-level intent into embodied action.

It surveys the background from psychology, artificial intelligence, and neurobiology, then organizes the technical landscape around those three components. It also discusses a cognitive core and future directions emphasizing ability, interpretability, generalizability, and evolvability.

## Relevance

For this vault, the main value is conceptual rather than empirical. The paper provides a language for comparing classical autonomy pipelines with more integrated or cognition-inspired systems.

That is especially relevant when reading hybrid racing stacks, where [[high_speed_perception]], [[autonomous_racing_planning]], and [[autonomous_racing_control]] are often designed separately but still have to function as one embodied closed-loop system.

## Notes / Critique

The strength of the paper is breadth. It gives a clean vocabulary for discussing how navigation systems should integrate perception, task reasoning, and action.

Its limitation is also breadth: it is a high-level review, not a racing-specific method paper, and it does not directly resolve the hard quantitative tradeoffs that appear in near-limit autonomous racing.

## Pages Created From This Source

- [[cognitive_navigation]]
- [[cognitive_navigation_review]]
