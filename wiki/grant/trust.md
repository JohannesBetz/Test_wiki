---
tags: [grant]
date: 2026-05-26
sources: 1
grant_id: "949796"
acronym: "TRUST"
host_institution: "Technische Universiteit Delft"
start_date: "2021-04-01"
end_date: "2026-07-31"
funding_scheme: "ERC-STG - Starting Grant"
total_budget: "1,499,515.00 EUR"
---

# TRUST

## Project Metadata

| Key | Value |
| --- | --- |
| **Title** | Control without Trust: A Distributionally Robust Approach |
| **Acronym** | TRUST |
| **Grant ID** | 949796 |
| **Host Institution** | Technische Universiteit Delft (Netherlands) |
| **Funding Scheme** | ERC-STG - Starting Grant |
| **Funding Programme** | H2020-EU.1.1. - EXCELLENT SCIENCE - European Research Council (ERC) |
| **DOI** | `10.3030/949796` |
| **EC Signature Date** | 2020-10-26 |
| **Start Date** | 2021-04-01 |
| **End Date** | 2026-07-31 |
| **Total Cost / EU Contribution** | EUR 1,499,515.00 |
| **CORDIS Permalink** | [cordis.europa.eu/project/id/949796](https://cordis.europa.eu/project/id/949796) |

## Objective

TRUST develops a control paradigm based on distributionally robust optimization.

The core idea is to design data-driven control methods that remain reliable when the true uncertainty distribution is not known exactly. Rather than trusting one nominal stochastic model, the project studies decisions that stay robust across a family of probability distributions consistent with the available information.

According to the CORDIS project and reporting pages, the project combines:

1. robust decision-making models from operations research,
2. dynamic-programming and control-theoretic characterizations,
3. and real-time computational tools from machine learning.

The stated target is scalable and provably reliable data-driven control for industrial-scale applications.

## Relevance to the Vault

This grant is not an autonomous-racing grant in the direct sense that [[agileflight]] is for drone racing, but it is highly relevant to the vault's broader control and extreme-autonomy questions.

Its main contribution is conceptual:

- it strengthens the `distribution shift matters` view of control,
- it pushes beyond nominal control toward decision-making under ambiguity,
- and it fits naturally with the vault's interest in high-speed, high-consequence systems where model mismatch can become catastrophic.

In the current wiki, the most natural nearby anchors are:

- [[autonomous_racing_control]], where uncertainty-aware control is already emerging as a central concern,
- [[risk_averse_model_predictive_control]], which handles uncertainty and tail-risk explicitly in racing control,
- [[a_harmonized_approach_beyond_the_limit_control_for_autonomous_vehicles_balancing_performance_and_safety_in_unpredictable_environments]], which argues that performance and safety must be co-designed under unpredictable conditions,
- and [[formulazero_distributionally_robust_online_adaptation_via_offline_population_synthesis]], which is the clearest explicitly distributionally robust racing paper currently in the vault.

## Related Models / Topics / Techniques

- [[autonomous_racing_control]]
- [[model_predictive_control]]
- [[risk_averse_model_predictive_control]]
- [[Highly_dynamic_autonomous_system]]
- [[formulazero_distributionally_robust_online_adaptation_via_offline_population_synthesis]]

## Notes

The important thing about TRUST for this vault is not one benchmark result, but the research direction it legitimizes: control under uncertain, shifting, only partially trusted data-generating conditions.

That is a very natural fit for autonomous racing, agile robotics, and other highly dynamic systems, where being wrong about the disturbance model or the environment distribution is often exactly what causes failure near the limit.
