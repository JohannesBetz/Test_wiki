---
tags: [technique]
date: 2026-05-13
sources: 1
---

# Adversarial Theory of Mind

## Definition

Adversarial theory of mind is a decision-making approach in which an autonomous agent reasons not only about another agent's future motion, but about that agent's latent intent, strategic beliefs, or possibly misleading outward behavior.

In safety-critical driving, this is useful when interaction quality depends on recognizing that another road user may be acting strategically rather than transparently.

## Key Approach

[[learning_what_they_pretend_to_think_adversarial_tom_for_safety_critical_driving_policies]] is the anchor paper for this technique in the vault.

The essential move is to treat interaction as an epistemic game:

- the ego agent observes another agent's behavior,
- but does not assume that observed behavior fully reveals true intent,
- and therefore learns a policy that remains safer or more robust under strategic ambiguity.

This places the technique between pure motion prediction and full game-theoretic reasoning. It asks not only "what will the other agent do?" but also "what does the other agent want me to believe?"

## Relationship to Driving and Racing Planning

This technique belongs most naturally near [[autonomous_racing_planning]] and [[cognitive_navigation]], especially their interaction-heavy branches.

Compared with [[neural_nonlinear_opinion_dynamics]], it leans more toward adversarial latent-intent reasoning than rapid decision commitment.

Compared with [[dynamic_near_potential_functions]], it leans more toward theory-of-mind robustness than approximate equilibrium search over maneuver parameters.

## Representative Papers

- [[learning_what_they_pretend_to_think_adversarial_tom_for_safety_critical_driving_policies]]

## Open Problems

Open problems include how to infer latent intent under noisy perception, how to distinguish genuine uncertainty from strategic deception, how to scale theory-of-mind reasoning beyond pairwise encounters, and how to verify that such policies improve safety rather than only shifting failure modes into harder-to-interpret interaction errors.
