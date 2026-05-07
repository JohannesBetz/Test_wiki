---
tags: [technique]
date: 2026-05-07
sources: 1
---

# Alternating Phases Curriculum Learning

## Definition

Alternating Phases Curriculum Learning, or APCL, alternates reverse and forward curriculum phases so an agent sees both achievable expert-proximal tasks and broadened challenging initial states.

## Key Approaches

In [[learn_consolidate_dominate_orchestrating_cognitive_skill_distillation_and_alternating_learning_for_autonomous_racing]], APCL divides a race track into corner and straight segments.

Reverse curriculum begins near easier, goal-proximal track phases: an expert guide policy handles earlier segments, while the RL policy handles the remaining segments. As performance improves, the handoff point moves backward until the RL policy handles the whole track.

Forward curriculum broadens the starting state distribution for the current phase by adding Gaussian noise estimated from non-optimal expert trajectories. This improves robustness beyond a single best expert lap.

## Representative Papers

- [[learn_consolidate_dominate_orchestrating_cognitive_skill_distillation_and_alternating_learning_for_autonomous_racing]]

## Open Problems

APCL relies on expert trajectories, track segmentation, performance thresholds, and switching criteria. It may need substantial adaptation for multi-agent racing or unseen tracks.
