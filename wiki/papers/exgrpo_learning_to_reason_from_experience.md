---
tags: [paper]
date: 2026-05-27
task: ai_systems
venue: "arXiv preprint"
sources: 1
year: "2025"
doi: "10.48550/arXiv.2510.02245"
url: "https://doi.org/10.48550/arXiv.2510.02245"
topic:
  - era_of_experience
  - foundation_models_for_intelligent_decision_making
tech_backbone: [large_language_models]
tech_representation: []
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: [reinforcement_learning]
tech_inference: []
datasets_used: []
models_used: []
hardware_used: []
simulators_used: []
---

# ExGRPO: Learning to Reason from Experience

> ExGRPO: Learning to Reason from Experience | arXiv 2025 | Runzhe Zhan, Yafu Li, Zhi Wang, Xiaoye Qu, Dongrui Liu, Jing Shao, Derek F. Wong, and Yu Cheng

## Summary

This paper proposes `ExGRPO`, a method for improving reasoning models by learning from experience rather than relying only on static supervised reasoning data.

That is why it matters for this vault. It extends the `era of experience` argument into a part of AI that is often treated as separate from embodied interaction:

**reasoning itself may become stronger when it is shaped by accumulated experience rather than only by human-written traces.**

## Method

The core method is [[exgrpo]].

At a high level, the paper appears to adapt reinforcement-learning-style reasoning optimization so that prior outcomes and accumulated experience play a more central role in how the reasoning model improves over time.

For the vault, the exact benchmark details matter less than the architectural claim:

- reasoning models should not only imitate good solutions,
- they should also improve from the consequences of their own learning process,
- and `experience` can be treated as a reusable substrate even in symbolic reasoning domains.

This places the paper in an interesting middle ground:

- not classical embodied RL,
- not pure language-model pretraining,
- but a hybrid experience-centered approach to reasoning improvement.

## Key Results

The strongest contribution is strategic rather than domain-specific.

This paper suggests that experience-driven learning is not only relevant for robots, racecars, or agents acting in environments. It may also matter for the improvement of reasoning-capable language models themselves.

That broadens the experience discussion in the vault. Experience is no longer only about control or embodiment; it also becomes a candidate ingredient for stronger abstract reasoning.

## Hardware Used

- No specific demonstration hardware is identified on the current page.


## Related Work

This paper belongs near [[welcome_to_the_era_of_experience]] and [[scaling_agent_learning_via_experience_synthesis]], but it plays a distinct role.

- [[welcome_to_the_era_of_experience]] argues for experience as the future substrate of AI.
- [[scaling_agent_learning_via_experience_synthesis]] asks how experience can be scaled more efficiently.
- [[exgrpo_learning_to_reason_from_experience]] asks whether reasoning models themselves can improve from experience.

It also belongs near [[limits_of_deep_learning_sequence_modeling_through_the_lens_of_complexity_theory]] as a partial response to the reasoning-limits discussion: if current models are weak reasoners, experience-shaped optimization is one plausible attempt to improve them, even if it does not yet resolve deeper architectural limits.

## Notes / Critique

The paper is exciting because it refuses the easy split between `language reasoning` and `experience-based learning`.

The main caution is evaluation. Many reasoning methods appear stronger because they optimize benchmark style, response format, or reward proxies rather than genuine reasoning depth.

So the interesting question is not only whether ExGRPO improves scores, but whether it genuinely teaches models to reason better from experience rather than merely adapt more aggressively to evaluation regimes.
