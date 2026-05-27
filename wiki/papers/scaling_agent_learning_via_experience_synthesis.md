---
tags: [paper]
date: 2026-05-27
task: ai_systems
venue: "arXiv preprint"
sources: 1
year: "2025"
doi: "10.48550/arXiv.2511.03773"
url: "https://doi.org/10.48550/arXiv.2511.03773"
topic:
  - era_of_experience
  - foundation_models_for_intelligent_decision_making
  - ai_agents_for_autonomous_systems
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

# Scaling Agent Learning via Experience Synthesis

> Scaling Agent Learning via Experience Synthesis | arXiv 2025 | Zhaorun Chen, Zhuokai Zhao, Kai Zhang, Bo Liu, Qi Qi, Yifan Wu, Tarun Kalluri, Sara Cao, Yuanhao Xiong, Haibo Tong, Huaxiu Yao, Hengduo Li, Jiacheng Zhu, Xian Li, Dawn Song, Bo Li, Jason Weston, and Dat Huynh

## Summary

This paper argues that agent learning can be scaled not only by gathering more online interaction, but by synthesizing additional useful experience from what an agent has already seen or done.

That makes it a particularly important paper for this vault. It takes the broad claim of [[welcome_to_the_era_of_experience]] and pushes it into a more operational direction:

**If experience is the future substrate of intelligence, then the next bottleneck becomes how to multiply the learning value of limited experience.**

## Method

The core proposal is [[experience_synthesis]].

The paper is best understood as a bridge between two traditions:

- the experience-centered view that agents must learn from interaction,
- and the foundation-model / agentic-AI view that generative systems may help structure, extend, or augment that learning process.

Instead of treating experience as a fixed stream of logged transitions, the paper asks whether agents can generate additional training signal through synthetic or recomposed experience that still improves downstream policy or decision quality.

For the vault, the important framing is not one specific benchmark number. It is the architectural move:

- real experience remains the grounding source,
- synthesis is used to scale or enrich that source,
- and agent learning becomes less tied to the raw throughput of expensive interaction alone.

## Key Results

The strongest contribution is conceptual and strategic.

This paper makes the `era of experience` thesis more concrete by proposing a scaling mechanism for agent learning. If the idea works, then experience-driven systems may not need to choose only between:

- expensive real interaction,
- or static human-generated corpora.

They may instead bootstrap richer learning from a smaller amount of grounded interaction.

For this vault, that matters because many of our most safety-critical domains, such as autonomous racing, drone flight, and embodied robotics, are limited by the cost and risk of real-world data collection.

## Hardware Used

- No specific demonstration hardware is identified on the current page.


## Related Work

This paper belongs directly near [[welcome_to_the_era_of_experience]], but it plays a different role.

- [[welcome_to_the_era_of_experience]] is the manifesto: why AI must move beyond human data.
- [[scaling_agent_learning_via_experience_synthesis]] is the scaling question: how to make experience-rich learning practical when direct interaction is costly.

It also belongs near [[foundation_models_and_intelligent_decision_making_progress_challenges_and_perspectives]] and [[llm_and_ai_agents_for_autonomous_systems_a_survey_of_applications_datasets_and_security_challenges]], because it suggests a concrete way that generative or agentic model families may contribute to autonomy without directly replacing the lower-level control stack.

## Notes / Critique

The paper's appeal is obvious: it tries to make experience-driven AI more scalable.

The main concern is epistemic drift. Synthetic experience is only useful if it preserves the right structure of the world, task, and consequences. Otherwise, the method risks producing more training data but less truth.

So the paper is exciting, but it should be read with a clear caution:

**experience synthesis is promising only to the extent that it remains anchored to real experience rather than becoming a closed synthetic loop.**
