---
tags: [source]
date: 2026-05-26
sources: 1
---

# Luo SONIC Motion Tracking Source

> Source: `raw/pdfs/Luo_SONIC_motion_tracking.pdf`
> Paper: SONIC: Supersizing Motion Tracking for Natural Humanoid Whole-Body Control, arXiv 2025

## Summary

This paper studies how humanoid motion tracking can be scaled up to support more natural whole-body control rather than only a narrow subset of trackable behaviors.

For this vault, it matters because it extends the humanoid branch from `can a robot track one difficult motion class?` toward `can motion tracking itself become broad and natural enough to anchor whole-body humanoid control?`

## Method

The training backbone is [[reinforcement_learning]].

The paper centers on [[sonic]], a humanoid motion-tracking framework aimed at natural whole-body control.

From the local PDF metadata and project-page support, the important framing is:

- supersized motion tracking,
- natural humanoid whole-body behavior,
- and real-world humanoid deployment on Unitree G1.

For this vault, the key point is that motion tracking is treated not as a narrow benchmarking tool, but as a route toward a larger behavior envelope for humanoids.

## Evaluation

The local metadata directly links the paper to the Unitree G1 humanoid and a public project page, which is enough to place it confidently in the real humanoid branch.

The broader takeaway is that humanoid control is increasingly being organized around how large and natural a motion-tracking regime can become, not only around locomotion, parkour, or isolated expressive skills.

## Notes / Critique

The strongest contribution appears to be scale and breadth. This paper gives the vault another argument that motion tracking is not just a subroutine for imitation demos, but a central systems path toward more natural humanoid behavior.

The main caveat is that this ingest is anchored to clean local PDF metadata rather than a full local text parse. So I’ve kept the note focused on the reliable high-level picture rather than fine implementation details.

## Pages Created From This Source

- [[sonic_supersizing_motion_tracking_for_natural_humanoid_whole_body_control]]
- [[sonic]]
