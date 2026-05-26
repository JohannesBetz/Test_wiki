---
tags: [paper]
date: 2026-05-13
task: ai_systems
venue: "IEEE Open Journal of Intelligent Transportation Systems 2026"
sources: 1
year: "2026"
doi: "10.1109/OJITS.2026.3665677"
topic:
  - foundation_models_for_intelligent_decision_making
  - ai_agents_for_autonomous_systems
  - Highly_dynamic_autonomous_system
tech_backbone: [large_language_models]
tech_representation: []
tech_generation: [foundation_models_for_intelligent_decision_making]
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
hardware_used: []
simulators_used: []
---

# LLM and AI Agents for Autonomous Systems: A Survey of Applications, Datasets, and Security Challenges

> LLM and AI Agents for Autonomous Systems: A Survey of Applications, Datasets, and Security Challenges | IEEE Open Journal of Intelligent Transportation Systems 2026 | Mohamed Amine Ferrag, Abderrahmane Lakas, Norbert Tihanyi, and Merouane Debbah

## Summary

This paper surveys the use of large language models and AI agents in autonomous systems, with special attention to datasets, benchmarks, and security challenges.

Its main value for this vault is that it expands the foundation-model discussion from capability and deployment into a more agentic and adversarial framing: once LLM-like systems begin to coordinate decisions or actions inside autonomy stacks, security and robustness become first-class issues.

## Method

The paper is a survey structured around applications, datasets, and security.

That combination matters because it keeps three perspectives together:

- where LLMs and agents may help autonomous systems,
- what data and benchmarks exist to evaluate them,
- and how their inclusion changes the system's risk profile.

For this vault, that makes it a useful bridge between intelligent-decision surveys and the harder engineering question of whether agentic autonomy can be made trustworthy enough for real deployment.

## Key Results

The strongest contribution is not a single empirical claim but a systems-level synthesis: LLMs and AI agents may become important components of autonomous systems, but their integration also creates new vulnerabilities and evaluation demands.

For this vault, the central takeaway is that agentic autonomy should be judged not only by capability or generality, but also by benchmark quality, attack surface, and operational reliability.

## Hardware Used

- No specific demonstration hardware is identified on the current page.


## Related Work

This paper belongs near [[foundation_models_for_intelligent_decision_making]], but it is more explicit than most of that branch about agents, datasets, and security.

Compared with [[foundation_models_in_robotics_applications_challenges_and_the_future]], it is less focused on robotics as such and more focused on autonomous systems broadly, including transportation and UAV-related contexts.

Compared with [[human_vs_machine_behavioral_differences_between_expert_humans_and_language_models_in_wargame_simulations]], it is less behaviorally specific, but it reinforces the same warning: an agent or LLM that appears capable at a high level may still create serious downstream risk when trusted with decision authority.

## Notes / Critique

The strongest contribution is that it makes security central rather than optional. That is especially important in autonomous systems, where agent-like models may become powerful long before they become well calibrated.

For the vault, this paper helps prevent the foundation-model branch from drifting into a pure capability narrative.
