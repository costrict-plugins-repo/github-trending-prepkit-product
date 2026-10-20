# Metric Tree Construction

## Structure

```
North Star Metric
├── Input Metric 1 — Breadth (how many users reach value)
│   ├── Leaf: acquisition channel conversion rate
│   └── Leaf: onboarding completion rate by segment
├── Input Metric 2 — Depth (how much value per session)
│   ├── Leaf: core feature adoption rate
│   └── Leaf: average sessions per active user
└── Input Metric 3 — Frequency (how often users return)
    ├── Leaf: D7 / D30 retention rate
    └── Leaf: notification or re-engagement click rate
```

---

## Construction Checklist

- [ ] Start with the North Star — not with existing dashboards
- [ ] Identify 3–5 input metrics that causally drive the North Star
- [ ] For each input, identify leaf metrics: specific actions one team can own and move
- [ ] For each leaf, verify: Is it actionable? Does one team own it? Can we measure it today?
- [ ] Confirm: if a team improved this leaf by 10%, would the input metric visibly move?
- [ ] Cap total leaf metrics at 15 — more creates noise and dilutes focus

---

## Leaf Metric Quality Test

Ask all four questions for each candidate leaf:

| Question | Pass Condition |
|---|---|
| Is it actionable? | A team can run an experiment to move it |
| Is ownership clear? | One team is responsible — no shared ownership |
| Is it measurable now? | Instrumentation exists or can be built in <1 sprint |
| Does it causally connect upward? | Movement in this leaf predicts movement in the input metric |

Fail on any question → remove or redesign the leaf.

---

## Common Mistakes

| Mistake | Consequence | Fix |
|---|---|---|
| More than 15 leaf metrics total | Teams lose focus; everything feels equal priority | Cap at 15; cut or merge leaves |
| Leaf metrics with no single owner | Nobody feels accountable; metrics drift | Assign one team to each leaf before publishing |
| Building tree top-down without data availability check | Tree looks good; half the leaves can't be measured | Validate instrumentation at leaf level before finalising |
| Confusing correlation with causation in the tree | Teams optimise leaves that don't actually move inputs | Run holdout experiments to validate causal links before committing |
| Copying another product's metric tree | Inputs vary by business model and user behaviour | Derive from your specific North Star and user jobs |
