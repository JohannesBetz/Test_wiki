---
tags: [source]
date: 2026-05-13
sources: 1
---

# BI Learning What They Pretend to Think Source

> Source: `raw/pdfs/BI_Learning_What_They_Pretend_to_Think_Adversarial_ToM_for_Safety-Critical_Driving_Policies.pdf`
> Paper: Learning What They Pretend to Think: Adversarial ToM for Safety-Critical Driving Policies

## Summary

This paper appears to study interactive driving through an adversarial theory-of-mind lens. The core idea, suggested clearly by the title, is that a driving policy should not only react to what other agents do, but reason about what they may be strategically signaling, hiding, or pretending in safety-critical interaction.

That makes it relevant to the vault's broader behavioral-planning branch, especially where fast autonomous decisions depend on anticipating the intentions of other vehicles rather than treating them as passive moving obstacles.

## Method

The likely methodological contribution is [[adversarial_theory_of_mind]], positioned as a way to learn driving policies that remain robust when other agents are interactive, strategic, or partly deceptive.

Within the logic of this vault, that places the paper near:

- behavioral planning in [[autonomous_racing_planning]],
- multi-agent tactical reasoning,
- and adjacent cognitive-decision approaches where the agent must model another actor's latent intent rather than only predict motion.

## Evaluation

Even without a clean local text extraction, the title alone makes the evaluation setting legible at a high level: the paper is about safety-critical driving policies, so the relevant stress test is whether intent-aware adversarial reasoning improves policy quality in close, high-consequence interaction scenarios.

That suggests a useful contrast with papers in the vault that emphasize:

- tactical commitment from inverse games, such as [[neural_nonlinear_opinion_dynamics]],
- or game-theoretic maneuver optimization, such as [[dynamic_near_potential_functions]].

## Notes / Critique

The main value of this source for the vault is conceptual. It strengthens the idea that autonomous driving competence may depend on a model of what others intend, not only where they are.

The main limitation of this ingest is technical rather than conceptual: the local PDF's text layer was not cleanly extractable in this workspace, so this source note is intentionally conservative and theme-level rather than a deep paper reconstruction.

## Pages Created From This Source

- [[learning_what_they_pretend_to_think_adversarial_tom_for_safety_critical_driving_policies]]
- [[adversarial_theory_of_mind]]
