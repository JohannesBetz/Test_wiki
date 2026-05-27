---
tags: [analysis, grant]
date: 2026-05-27
sources: 12
---

# ERC Starting Grant - Proposal Outline (Part B1 Synopsis)

This document provides a structured, page-by-page outline for the 5-page Extended Synopsis (Part B1) based on the core thesis from [[erc_idea]]. It integrates design patterns from successful grants in the vault to maximize appeal to both generalist and specialist reviewers.

---

## Page 1: The Bottleneck, Vision, & The "Hook"

### 1.1 The Core Scientific Paradox (First Paragraph)
*   **The Hook:** Start with a clear statement of the conflict: *How can autonomous systems learn from interaction to exceed elite human capability at the physical limits of handling without experiencing catastrophic failures during the exploration phase?*
*   **The Vision:** Introduce the concept of **Structured Experience-Driven Autonomy**—a hybrid framework that embeds reinforcement learning within distributionally robust optimization and metacognitive safety wrappers.

### 1.2 State-of-the-Art (SotA) & Gaps
*   Identify the limits of the current SotA:
    *   *Classical Control:* Safe but conservative; relies on perfect nominal models and cannot adapt to real-time dynamic changes (e.g., tire degradation or wind).
    *   *End-to-End Deep Learning:* Exceptional performance in simulation, but highly brittle, opaque, and unsafe during real-world physical exploration.
*   **The Scientific Gap:** The lack of a unified paradigm that couples perception, learning, and control theory under distribution shifts and physical degradation.

### 1.3 Key Architectural Diagram
*   *Visual Concept:* A high-quality schematic showing the information flow:
    *   **Outer Loop:** Multisensory Active Perception & Policy Learning (extracting features from environment interaction).
    *   **Inner Loop:** Distributionally Robust MPC & Safety Envelope (guaranteeing physical viability and handling limit enforcement).
    *   **Feedback Link:** Metacognitive failure regulation adjusting objectives when hardware is degraded.

---

## Page 2: Research Pillars & Scientific Ambition

### 2.1 Primary Objectives
Formulate three distinct, measurable scientific objectives:
1.  **Objective 1 (Holistic Perception-Action Co-design):** Formulate algorithms that co-design low-latency sensing (e.g., event-based features) directly with reinforcement learning policies to operate near the physics-limit.
2.  **Objective 2 (Distributionally Robust limit Handling):** Formulate data-driven controllers that adapt to dynamic envelope shifts and model mismatches using distributionally robust optimization.
3.  **Objective 3 (Metacognitive Self-Regulation):** Create self-regulation architectures that allow the robot to comprehend, isolate, and adapt to internal hardware malfunctions in real time.

### 2.2 Ground-Breaking Nature (High-Risk/High-Gain)
*   *Why this is ground-breaking:* It shifts the paradigm from "avoiding limits" to "safely exploiting limits" via structured experience.
*   *Why it is high-risk:* Operating on the edge of handling means model mismatch is catastrophic; physical interaction is expensive and dangerous.
*   *Why it is high-gain:* Unlocks superhuman performance in critical, unstructured environments (rescue, agile flight, high-speed transit).

---

## Page 3: High-Level Methodology & Risk Mitigation (Plan B)

### 3.1 Methodological Framework
*   **Phase 1: Safe RL in Differentiable Simulators.** Describe how the agent learns initial policy weights using physics-grounded simulators.
*   **Phase 2: Hybrid Dynamics & Telemetry Alignment.** Explain how the model combines learned dynamics with physical principles to ensure smooth sim-to-real transfer.
*   **Phase 3: Real-Time Envelope Exploitation.** Detail the integration of Deep RL with Model Predictive Contouring Control (MPCC).

### 3.2 Risk-Mitigation Strategy (Plan B)
Show reviewers that you have structured control over the project's risks:
*   *Risk:* The reinforcement learning agent executes an unsafe action during real-world exploration.
    *   *Plan B:* Embed the policy within an active **Control Barrier Function (CBF)** or safe backup MPC wrapper that overrides the agent if it attempts to exit the viable dynamic envelope.
*   *Risk:* Sim-to-real mismatch causes immediate instability on hardware.
    *   *Plan B:* Use offline population synthesis and domain randomization based on distributionally robust bounds to prepare the policy for a wide family of physical parameters.

---

## Page 4: System Integration & Embodied Validation

### 4.1 Holistic System Cohesion
*   Demonstrate that the three research pillars are not separate tasks, but feedback into one another:
    *   Pillar 1 (Perception) feeds Pillar 2 (Control) with low-latency state representations.
    *   Pillar 2 (Control) provides safe exploration bounds for Pillar 1 (Learning).
    *   Pillar 3 (Metacognition) adjusts the objectives of Pillar 2 when the system undergoes degradation (e.g., motor loss or sensor failure).

### 4.2 Real-World Experimental Testbeds
Detail the physical platforms that will validate the proposed framework:
1.  **Platform A (Agile Flight):** Event-camera-equipped quadrotors navigating dense obstacle courses at high speed (building on [[agileflight]]).
2.  **Platform B (Legged Locomotion):** Quadrupedal robots executing dynamic jumps and slips on crumbling terrain (building on [[lemo]]).
3.  **Platform C (High-Speed Racing):** 1:5 scale autonomous racecars driving on the traction limit with dynamic tire degradation (building on [[autonomous_racing_control]]).

---

## Page 5: PI Competence & Strategic Synthesis

### 5.1 Why the PI? (Unique Expertise)
*   Highlight your unique background bridging control theory, machine learning, and physical robotics.
*   Cite previous key publications that prove you have already achieved foundational results in limit control or online adaptation (e.g., linking back to your papers in [[Highly_dynamic_autonomous_system]]).

### 5.2 Broader Scientific Impact
*   Explain how the algorithms developed in this project will transfer to other high-consequence industries (e.g., autonomous driving, aerospace safety, planetary exploration).
*   Reiterate the final pitch: This project will establish the mathematical and physical foundations of experience-driven autonomy, proving that machines can safely outperform human experts in the world's most challenging environments.
