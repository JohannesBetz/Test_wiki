---
tags: [paper]
date: 2026-05-27
task: Highly_dynamic_autonomous_system
venue: "arXiv preprint"
sources: 1
year: "2026"
doi: "10.48550/arXiv.2605.22748"
url: "https://doi.org/10.48550/arXiv.2605.22748"
topic:
  - autonomous_drone_racing
  - reinforcement_learning
  - Highly_dynamic_autonomous_system
tech_backbone: [reinforcement_learning]
tech_representation: []
tech_generation: []
tech_conditioning: []
tech_modality_alignment: []
tech_finetuning: []
tech_inference: []
datasets_used: []
models_used: []
hardware_used: [drones]
simulators_used: [quadrotor_simulation]
---

# Superhuman Safe and Agile Racing through Multi-Agent Reinforcement Learning

> Superhuman Safe and Agile Racing through Multi-Agent Reinforcement Learning | arXiv 2026 | Ismail Geles, Leonard Bauersfeld, Markus Wulfmeier, and Davide Scaramuzza

## Summary

This paper studies autonomous drone racing through a multi-agent reinforcement-learning setup aimed at producing behavior that is simultaneously faster than human reference, aggressively agile, and still safe enough to race competitively.

For this vault, that makes it one of the clearest `post-Swift` racing papers in the aerial branch. It shifts the focus from solo high-speed lap execution toward interactive competitive racing learned through multi-agent training.

## Method

The core approach is multi-agent [[reinforcement_learning]] for drone racing.

From the local PDF metadata and citation structure, the paper appears to sit in the AGILEFLIGHT / RPG lineage and connect naturally to:

- prior solo RL racing milestones,
- multi-agent learning frameworks,
- and recent work on agile flight from pixels without explicit state estimation.

The important conceptual move is not just `train a faster policy`. It is:

- train in a competitive multi-agent regime,
- preserve aggressive racing behavior,
- and build safety into the learned racing behavior rather than bolt it on afterward.

## Key Results

The strongest takeaway, from the vault's perspective, is that competitive drone-racing competence is increasingly becoming a multi-agent learning problem rather than only a single-agent time-trial problem.

The paper also matters because it sharpens the field's benchmark language:

- `superhuman` suggests the performance target,
- `agile` emphasizes the dynamic-control difficulty,
- and `safe` signals that the policy is being evaluated not only on speed but also on whether it survives competitive interaction.

That combination is exactly what makes the result useful to the broader high-dynamics branch.

## Hardware Used

- [[drones]]

## Funding / Grants

- Supported by the European Research Council (ERC) Consolidator Grant [[agileflight]].

## Related Work

This paper belongs most directly near [[champion_level_drone_racing_using_deep_reinforcement_learning]].

- [[champion_level_drone_racing_using_deep_reinforcement_learning]] established that onboard RL could beat world champions in physical drone racing.
- [[superhuman_safe_and_agile_racing_through_multi_agent_reinforcement_learning]] appears to push the branch further toward explicitly multi-agent competitive learning.

It also sits near [[dashing_for_the_golden_snitch_multi_drone_time_optimal_motion_planning_with_multi_agent_reinforcement_learning]], but with a different emphasis: the Golden Snitch paper is about multi-agent time-optimal planning in shared airspace, while this paper is more explicitly about competitive racing behavior under safety and agility constraints.

## Notes / Critique

The paper is exciting because it pushes drone racing toward the same kind of multi-agent competitive sophistication that made systems like GT Sophy interesting in simulator racing.

The main caveat is that multi-agent RL can look stronger than it generalizes. The hardest questions are still whether the learned policy remains robust against unseen opponents, different tracks, and small shifts in sensing or dynamics, and whether its notion of `safe` remains stable under those changes.
