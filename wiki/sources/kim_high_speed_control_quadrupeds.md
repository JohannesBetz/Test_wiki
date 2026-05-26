---
tags: [source]
date: 2026-05-22
sources: 1
---

# Kim High-Speed Control Quadrupeds Source

> Source: `raw/pdfs/Kim_High-speed-control_quadrupeds.pdf`
> Paper: High-speed control and navigation for quadrupedal robots on complex and discrete terrain, arXiv 2025

## Summary

This paper studies how a quadrupedal robot can move quickly and navigate reliably over terrain that is both complex and discrete rather than smooth and forgiving.

For this vault, the paper matters because it extends the high-speed-autonomy discussion beyond racecars and drones into legged robotics. It suggests that extreme embodied autonomy is not only about going fast on prepared tracks, but also about maintaining control and navigation quality when the environment is irregular, discontinuous, and physically punishing.

## Method

The metadata clearly supports the paper's central framing: `high-speed control` and `navigation` are treated together rather than as separate subproblems.

That is an important design signal for the vault. On complex terrain, a quadruped cannot afford a clean separation where planning ignores execution and control ignores terrain structure. The likely architectural emphasis is therefore on tight coupling between:

- terrain-aware navigation,
- fast locomotion control,
- and embodied stability on discrete foothold-like structures.

## Evaluation

The accessible local metadata does not expose the full experimental details cleanly in this workspace, but the title and arXiv framing strongly suggest a real or realistic high-speed quadrupedal evaluation on challenging terrain.

For the purposes of this vault, the key result is conceptual: quadrupedal robots belong in the same broader extreme-autonomy conversation as agile drones, rally vehicles, and racecars whenever success depends on fast embodied action under harsh terrain constraints.

## Notes / Critique

The strongest value of this ingest is scope expansion. It gives the wiki a cleaner quadruped branch inside [[Highly_dynamic_autonomous_system|highly dynamic autonomy]] and helps support the idea that extreme-environment autonomy is a cross-embodiment problem.

The main caveat is evidentiary. I recovered reliable title, author, and DOI metadata from the PDF itself, but the full text was not conveniently extractable in this workspace, so this source note stays intentionally method-level rather than pretending to reconstruct every experiment.

## Pages Created From This Source

- [[high_speed_control_and_navigation_for_quadrupedal_robots_on_complex_and_discrete_terrain]]
- [[quadrupedal_locomotion]]
