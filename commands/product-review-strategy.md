---
description: Review product artifacts for evidence quality, routing fit, specification rigor, opportunity decisions, and prioritization discipline.
argument-hint: [artifact path or scope]
---

Use the `product-strategy-reviewer` agent.

Workflow:
- Read `spec/product-context.md` as the primary context source.
- Activate the relevant domain skill(s) based on artifact type:
  - Discovery artifacts -> `product-discovery-synthesis` + `product-validation`
  - Research-design artifacts -> `product-user-interview-design`
  - Opportunity artifacts -> `product-opportunity-mapping`
  - PRD artifacts -> `product-prd-authoring`
  - Engagement or gamification artifacts -> `product-engagement-design`
  - Prioritization artifacts -> `product-prioritization`
  - Any artifact with metrics -> `product-metrics-analysis`
- Flag sections where `source: model` and `settled: false`.
- Flag any mismatch between shared-state sections and the route or artifact being recommended.
- Save review output to `./reports/`.
