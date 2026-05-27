---
tags: [paper]
date: 2026-05-27
task: general_ai
venue: "arXiv preprint"
sources: 1
year: "2026"
doi: "10.48550/arXiv.2603.15381"
url: "https://doi.org/10.48550/arXiv.2603.15381"
topic:
  - era_of_experience
  - foundation_models_for_intelligent_decision_making
  - artificial_general_intelligence
tech_backbone: [large_language_models]
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

# Why AI systems don't learn and what to do about it: Lessons on autonomous learning from cognitive science

> Why AI systems don't learn and what to do about it: Lessons on autonomous learning from cognitive science | arXiv 2026 | Emmanuel Dupoux, Yann LeCun, and Jitendra Malik

## Summary

This paper argues that present-day AI systems often do not `learn` in the deeper autonomous sense implied by cognitive science, even when they scale impressively on benchmarks.

For this vault, that matters a lot. It gives the experience branch a sharper critique:

**it is not enough for AI systems to optimize from more data; they may need a different kind of learning architecture if they are to become genuinely autonomous learners.**

## Method

This is a conceptual and architectural paper rather than a robotics benchmark or a new planner/controller.

Its main move is to diagnose the gap between current AI learning and richer notions of [[autonomous_learning]] drawn from cognitive science. The paper appears to ask:

- what autonomous learning should mean,
- why current systems fail to achieve it,
- and what design lessons cognitive science offers for building more self-directed learners.

That makes it especially useful as a bridge between broad AGI discussions and the more grounded experience-driven agenda in the rest of the wiki.

## Key Results

The strongest result is a reframing:

current AI systems may look impressive while still lacking key ingredients of autonomous learning.

In the vault's language, this paper helps distinguish between:

- systems that absorb and optimize over large human-produced corpora,
- and systems that genuinely accumulate, organize, and revise their own competence over time.

That is why the paper belongs so naturally next to [[welcome_to_the_era_of_experience]]. Silver and Sutton argue that experience is the next substrate. Dupoux, LeCun, and Malik argue that the field still lacks the right learning machinery to make that transition real.

## Hardware Used

- No specific demonstration hardware is identified on the current page.


## Related Work

This paper belongs directly near [[welcome_to_the_era_of_experience]], but the two papers play different roles.

- [[welcome_to_the_era_of_experience]] is the field-level trajectory claim: AI is moving from human data toward experience.
- [[why_ai_systems_dont_learn_and_what_to_do_about_it_lessons_on_autonomous_learning_from_cognitive_science]] is the critique: even with that aspiration, current systems may still not possess the right structure for autonomous learning.

It also belongs near [[agi_imagined_how_is_agi_configured_by_the_theories_of_mind]], because both papers ask what assumptions about mind and learning quietly shape our theories of AI progress.

## Notes / Critique

The paper is valuable because it raises the bar. It does not ask only whether AI systems can perform, but whether they can truly learn for themselves.

The main caveat is that it is more diagnostic than operational. It tells us a lot about what may be missing, but less about which concrete autonomy architecture already solves the problem.
