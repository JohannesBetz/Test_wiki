---
tags: [paper]
date: 2026-05-27
task: ai_systems
venue: "arXiv preprint"
sources: 1
year: "2025"
doi: "10.48550/arXiv.2507.22028"
url: "https://doi.org/10.48550/arXiv.2507.22028"
topic:
  - cognitive_navigation
  - era_of_experience
  - foundation_models_for_intelligent_decision_making
tech_backbone: [reinforcement_learning]
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

# From Seeing to Experiencing: Scaling Navigation Foundation Models with Reinforcement Learning

> From Seeing to Experiencing: Scaling Navigation Foundation Models with Reinforcement Learning | arXiv 2025 | Honglin He, Yukai Ma, Wayne Wu, and Bolei Zhou

## Summary

This paper argues that navigation foundation models should become stronger not only by seeing more data, but by accumulating more `experience` through reinforcement learning.

For this vault, that makes the paper a particularly clean bridge between two threads:

- foundation-model-style broad priors,
- and the era-of-experience claim that real competence must increasingly come from interaction.

## Method

The central move is to take navigation foundation models and push them from passive perception toward active experience.

That means the paper is best read as an architectural transition:

- pretrained or broad navigation priors provide the starting point,
- reinforcement learning provides the interaction loop,
- and navigation capability is scaled through experience rather than visual pretraining alone.

This makes it a natural fit for [[cognitive_navigation]], but with strong secondary relevance to [[foundation_models_for_intelligent_decision_making]] and [[era_of_experience]].

## Key Results

The strongest contribution is conceptual and directional.

The paper suggests that a promising path for embodied foundation models is not to stop at generalized visual understanding, but to close the loop through action and consequences.

For the vault, that matters because it operationalizes a question that appears repeatedly elsewhere:

**How do broad pretrained priors become grounded autonomous competence?**

This paper's answer is: by moving from seeing to experiencing.

## Hardware Used

- No specific demonstration hardware is identified on the current page.

## Related Work

This paper belongs near [[welcome_to_the_era_of_experience]], [[scaling_agent_learning_via_experience_synthesis]], and [[foundation_models_and_intelligent_decision_making_progress_challenges_and_perspectives]], but it plays a more specific role.

- [[welcome_to_the_era_of_experience]] is the broad historical thesis that AI must move beyond human data toward grounded interaction.
- [[scaling_agent_learning_via_experience_synthesis]] asks how experience-driven learning can be scaled efficiently.
- [[from_seeing_to_experiencing_scaling_navigation_foundation_models_with_reinforcement_learning]] applies that shift to navigation foundation models directly.

It also belongs near [[cognitive_navigation_review]], because it reinforces the view that strong navigation is not just perception plus routing, but a closed-loop perception-decision-action process.

## Notes / Critique

The paper is appealing because it gives the experience branch a concrete embodiment-facing example outside racing.

The main caveat is that the current local evidence supports a clean framing claim more than a mature deployment claim. So the page should currently be read as a strong bridge paper, not yet as proof that navigation foundation models have solved grounded generalization in the real world.
