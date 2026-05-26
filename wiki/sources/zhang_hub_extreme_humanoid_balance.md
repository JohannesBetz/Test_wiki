---
tags: [source]
date: 2026-05-26
sources: 1
---

# Zhang HuB Extreme Humanoid Balance Source

> Source: `raw/pdfs/Zhang_ HuB_Learning Extreme Humanoid Balance.pdf`
> Paper: HuB: Learning Extreme Humanoid Balance, CoRL 2025

## Summary

This paper studies how a humanoid can perform extreme balance behaviors that are easy for humans to recognize but hard for robots to execute robustly, such as stable single-leg poses and high kicks.

For this vault, the paper matters because it gives the humanoid branch a strong `balance-first` result rather than another locomotion-only or parkour-only success case.

## Method

The training backbone is [[reinforcement_learning]].

From the CoRL record and project-page abstract support, HuB combines three ingredients:

- reference motion refinement,
- balance-aware policy learning,
- and sim-to-real robustness training.

For this vault, the important point is that the paper treats extreme balance as a structured systems problem where motion quality, morphology mismatch, and deployment robustness all have to be handled together.

## Evaluation

The public record reports real-world validation on the Unitree G1 humanoid across challenging quasi-static balance tasks such as Swallow Balance, Bruce Lee's Kick, and related single-leg poses, including strong external disturbances.

For this vault, the useful takeaway is broader than one pose:

extreme humanoid balance can be learned as a robust deployable capability rather than only as a fragile demonstration under gentle conditions.

## Notes / Critique

The strongest contribution is the way the paper isolates balance as a primary competence instead of treating it as a side effect of general locomotion.

That makes it a strong complement to:

- [[real_world_humanoid_locomotion_with_reinforcement_learning]], which emphasizes stable locomotion transfer,
- [[humanoid_parkour_learning]], which emphasizes multi-skill obstacle traversal,
- and [[hiking_in_the_wild_a_scalable_perceptive_parkour_framework_for_humanoids]], which emphasizes perceptive outdoor traversal.

## Pages Created From This Source

- [[hub_learning_extreme_humanoid_balance]]
- [[hub]]
