---
tags: [source]
date: 2026-05-13
sources: 1
---

# Baumann ForzaETH Stack Source

> Source: `raw/pdfs/Baumann_ForzaETH_Stack.pdf`
> Paper: ForzaETH Race Stack—Scaled Autonomous Head-to-Head Racing on Fully Commercial Off-the-Shelf Hardware, Journal of Field Robotics 2025

## Summary

This paper presents the ForzaETH Race Stack, a full autonomous racing software platform for 1:10-scale head-to-head competition built entirely on commercial off-the-shelf hardware.

For this vault, the paper is especially useful because it is a true full-stack systems paper. Rather than isolating one planner, controller, or perception module, it focuses on how a reproducible scaled racing system can be assembled, operated, and adapted for both time-trial and unrestricted head-to-head racing.

## Method

The paper positions ForzaETH as an accessible but competitive alternative to more bespoke autonomous-racing systems.

Its main design choices are:

- scaled 1:10 racing on the [[f1tenth]] platform class,
- full head-to-head capability rather than only time trials,
- modular software components for perception, state estimation, planning, and control,
- and commercial off-the-shelf hardware to improve reproducibility and ease of adoption.

The abstract emphasizes adaptability to changing track layouts and friction conditions, suggesting that the stack is designed not only for one fixed benchmark but as a reusable research platform.

## Evaluation

The paper reports that the stack has won the official F1TENTH international competition multiple times and has been demonstrated on unusually large tracks for the scale, up to roughly 150 m.

For this vault, that makes the contribution both methodological and infrastructural: it is evidence that a carefully engineered scaled platform can still support serious autonomous-racing research without custom one-off hardware.

## Notes / Critique

The strongest contribution is reproducible systems engineering. Many racing papers assume substantial hidden integration work; this paper makes the stack itself the contribution.

Its limitation is also the familiar one for scaled platforms: even when the racing logic is strong, transfer to full-scale dynamics, sensing ranges, and safety constraints remains nontrivial.

## Pages Created From This Source

- [[forzaeth_race_stack_scaled_autonomous_head_to_head_racing_on_fully_commercial_off_the_shelf_hardware]]
- [[forzaeth_race_stack]]
