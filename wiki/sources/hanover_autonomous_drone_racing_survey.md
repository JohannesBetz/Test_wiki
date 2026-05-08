---
tags: [source]
date: 2026-05-08
sources: 1
---

# Hanover Autonomous Drone Racing Survey Source

> Source: `raw/pdfs/Hanover_Autonomous_Drone_Racing_A_Survey.pdf`
> Paper: Autonomous Drone Racing: A Survey, IEEE Transactions on Robotics 2024

## Summary

This paper surveys autonomous drone racing (`ADR`) as a benchmark for high-speed onboard perception, planning, control, and state estimation under severe sensing and computation constraints.

For this vault, it is a valuable companion to the Swift paper because it broadens the picture from one champion-level system to the evolution of the whole field, including both model-based and learning-based approaches.

## Method

The survey organizes the field around the classic flight stack:

- modeling and system identification,
- perception and state estimation,
- planning,
- control,
- learning-based methods,
- and simulation infrastructure.

It emphasizes the specific challenges that make drone racing hard: motion blur, high dynamic range, aerodynamic uncertainty, onboard compute limits, and the need to react on the timescale of tens of milliseconds.

## Evaluation

As a review, the contribution is synthesis rather than a benchmark score. The paper highlights how ADR has evolved through a series of competitions and research systems, and it frames racing lap time as a compact but demanding measure of progress in agile autonomy.

The survey also argues that drone racing is useful not only as a sport-like benchmark but as a proxy for real applications such as inspection, search and rescue, and aerial navigation in GNSS-denied or cluttered environments.

## Notes / Critique

The strongest part is breadth with engineering specificity. The survey does not stop at high-level taxonomy; it also discusses drone modeling, sensor limitations, and the interaction between hardware and algorithms.

Its main limitation for this vault is that it predates a few newer milestones, including some 2025 safety-assured flight work. So it works best as the historical map of the ADR field up to 2024, not as the last word on current state of the art.

## Pages Created From This Source

- [[autonomous_drone_racing_a_survey]]
