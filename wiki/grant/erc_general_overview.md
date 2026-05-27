---
tags: [concept]
date: 2026-05-27
sources: 0
---

# ERC General Overview

This page provides a comprehensive overview of the European Research Council (ERC) Starting Grant guidelines, proposal structures, evaluation criteria, and success strategies based on official European Commission and CORDIS references.

## Purpose of the Grant

The ERC Starting Grant is aimed at early-career researchers who are ready to establish their own independent research team or program in an EU Member State or Associated Country. 

## Eligibility Parameters

*   **Career Stage:** Early-career PIs who have successfully defended their first PhD.
*   **Window:** Standard eligibility is **2 to 7 years post-PhD** (extensions are allowed for maternity/paternity leave, long-term illness, clinical training, or national service). *Note: The ERC transitions to a 10-year post-PhD window starting in 2027.*
*   **Independence:** Demonstrated capacity for scientific independence, typically evidenced by having at least one major publication without the participation of the PhD supervisor.
*   **Time Commitment:** The PI must dedicate a minimum of **50% of their total working time** to the ERC project.
*   **Funding Size:** Up to **€ 1.5 million** for up to **5 years** (with an additional € 1 million available for startup costs, major equipment, or access to large facilities).

## Proposal Structure

An ERC Starting Grant application consists of three main parts:

### 1. Administrative Forms (Part A)
Contains structured data about the project, panel selection, host institution, ethical statements, and the detailed budget justification table.

### 2. Part B1 (Extended Synopsis & Track Record)
A stand-alone document (maximum 14-15 pages) designed for the first step of evaluation:
*   **Extended Synopsis (5 pages):** High-level summary explaining the project's ground-breaking nature and overall feasibility, written for a **generalist** panel.
*   **Curriculum Vitae (CV):** Detail-oriented record of education, career history, funding achievements, and leadership.
*   **Track Record:** Highlights up to 5 publications demonstrating independence (lead/senior authorship), along with patents, invited talks, or awards.

#### Designing a Convincing 5-Page Extended Synopsis
Because Part B1 is the sole document evaluated in Step 1, it acts as the primary gatekeeper. Panel members are often generalists within your broad domain (e.g. all of robotics, controls, and computer science), not specialists in your narrow sub-field. Successful proposals typically organize the 5 pages of the Extended Synopsis using a clear, narrative-driven outline:

*   **Page 1: The "Hook" & The Vision**
    *   *Abstract/Summary:* The core research question stated clearly and immediately in the first paragraph.
    *   *State-of-the-Art & Gaps:* Situating the project and defining the critical scientific bottleneck or gap that has prevented progress.
    *   *Visual Concept:* A high-quality graphic, diagram, or conceptual schematic summarizing the overall architecture.
*   **Page 2: The Core Objectives & Scientific Ambition**
    *   *Primary Objectives:* Clear, bulleted, and highly visible key objectives.
    *   *Ground-breaking Nature:* Explaining why the idea is revolutionary (high-gain) rather than incrementally developmental.
    *   *Why Now? / Why Me?:* Describing why this is the perfect historical moment for the research and why the PI has the unique cross-disciplinary skillset to lead it.
*   **Page 3: High-Level Methodology & Research Strategy**
    *   *Intellectual Framework:* The logical flow of the research tasks. (Detailed step-by-step methodologies are reserved for Part B2).
    *   *Feasibility & Risk Mitigation:* Acknowledge the high-risk nature. Detail a concrete "Plan B" (contingency strategy) for potential failure points to prove you have structured control.
*   **Page 4: Cohesion & Broader Impact**
    *   *Structural Cohesion:* Displaying how different work streams or objectives feedback into one another to form a unified scientific contribution.
    *   *Broader Impact:* The potential long-term transferability of the results to adjacent fields or industrial applications.
*   **Page 5: Synthesis & References**
    *   *Final Pitch:* Reiterate why the project represents a step-change.
    *   *References:* Essential literature citations demonstrating command of the state-of-the-art. (Check call specifications: key references are often excluded from the page count, but must be kept clean).

### 3. Part B2 (Detailed Scientific Proposal)
A detailed document (maximum 14 pages) reviewed in the second stage by panel members and external **specialists**:
*   **State-of-the-Art & Objectives:** Defining the scientific gap and how the project goes beyond existing limits.
*   **Methodology:** The work plan, work packages, resources, and risk-mitigation strategy (Plan B).

---

## Evaluation Criteria: "Scientific Excellence"

Scientific excellence is the **sole criterion** for evaluation, assessed across two dimensions:

### A. The Research Project
1.  **Ground-breaking Nature:** Ambition of goals, novelty of concepts/theories, and potential to redefine the field.
2.  **High-Risk/High-Gain:** Feasibility coupled with high potential rewards.
3.  **Methodology:** Appropriateness of the experimental design, milestones, and resources.

### B. The Principal Investigator (PI)
1.  **Intellectual Capacity:** Ability to propose and conduct creative, independent research.
2.  **Scientific Track Record:** Proven expertise and output relative to their career stage.
3.  **Commitment:** Dedication of at least 50% time to the project.

---

## Keys to an Outstanding Proposal

To succeed in the highly competitive selection process, proposals must go beyond generic grant writing:

*   **Design for Step 1 (Part B1):** The extended synopsis must capture generalist reviewers. It must explain *why* the problem is important and *why now* without getting lost in technical jargon.
*   **Defend the High-Risk/High-Gain Trade-off:** Reviewers want to see ambition. If a project is low-risk, it is deemed incremental and rejected. If it is high-risk without a safety net, it is deemed infeasible. Outstanding proposals provide a robust risk-mitigation strategy.
*   **Prove Autonomy:** The CV must clearly demonstrate that the candidate has stepped out of their PhD advisor's shadow and is ready to run an independent lab.
*   **Nail the Interview:** The Step 2 interview requires the PI to display leadership, defend their methodological choices under specialist questioning, and communicate their scientific vision with confidence.

---

## Lessons Learned from Existing Grants

An analysis of successful ERC grants archived in this vault—including [[agileflight]], [[interact]], [[lemo]], [[recover_me]], [[siren]], and [[trust]]—reveals critical design patterns that distinguish high-performing robotics and control proposals:

### 1. Rejecting Modularity in Favor of Holistic Systems
Reviewers strongly favor proposals that challenge traditional boundaries (e.g., separating perception, planning, and control as isolated components) in favor of co-designed, coupled systems:
*   **Active Perception-Action Loops:** Projects like [[agileflight]] and [[siren]] argue that physical limits (like low latency or dynamic manipulation) cannot be solved by modular pipelines. They co-design sensing (such as event-based cameras) directly with policy learning.
*   **Sim-to-Real Transfer:** Proving that complex behaviors can transfer directly from simulator to physical hardware under real-world constraints (e.g., [[lemo]]'s quadrupedal locomotion) grounds the scientific claims in physical reality rather than theoretical abstraction.

### 2. Framing Failure and Uncertainty as Core Intellect
Outstanding proposals do not treat hardware degradation or model mismatch as peripheral engineering issues, but as central challenges of autonomous intelligence:
*   **Metacognition and Self-Regulation:** [[recover_me]] proposes that a robot should have human-like metacognitive awareness to autonomously comprehend, troubleshoot, and recover from its own hardware malfunctions.
*   **Mathematical Robustness Under Ambiguity:** [[trust]] moves beyond nominal stochastic models, proposing distributionally robust control paradigms to systematically handle distribution shift and model mismatch at the limit of handling.

### 3. Anchoring Theory to Dynamic Physical Embodiment
All reviewed grants anchor complex mathematical or machine learning theory to demanding, highly intuitive physical tasks. Rather than presenting algorithms in a vacuum, they demonstrate validation on physical platforms (legged systems, high-speed quadrotors, mobile manipulators) facing high-consequence environments.

---

## Related Pages

- [[agileflight]] (ERC Consolidator Grant example)
- [[interact]] (Intuitive multi-robot interaction among humans)
- [[lemo]] (Reinforcement learning for real legged mobility)
- [[recover_me]] (Resilience and metacognition under failure)
- [[siren]] (Structured interactive perception and learning)
- [[trust]] (Distributionally robust control and decision-making)
- [[Highly_dynamic_autonomous_system]] (Contextual domain of APEX research)

