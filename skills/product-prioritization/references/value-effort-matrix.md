# Value-Effort Matrix

## Axis Definitions

| Axis | Meaning | Who Estimates |
|---|---|---|
| X — Effort | Time + complexity to build and ship | Implementers (engineering), not requesters |
| Y — Value | User or business outcome impact | Measured against a specific metric, not feature count |

Never let requesters estimate effort. Never let builders define value without outcome metrics.

---

## Quadrant Playbook

| Quadrant | Label | Action |
|---|---|---|
| High Value / Low Effort | Quick Wins | Do first — highest ROI per unit of time |
| High Value / High Effort | Strategic Bets | Plan carefully; validate assumptions before committing |
| Low Value / Low Effort | Fill-ins | Do only if capacity allows; do not prioritize over above |
| Low Value / High Effort | Avoid | Deprioritize or reject; re-examine if assumptions change |

---

## When the Matrix Misleads

| Signal | Problem | Fix |
|---|---|---|
| All items cluster in one quadrant | Criteria too coarse | Split dimensions (e.g., separate user value from revenue value) |
| Effort is "unknown" for most items | Estimates missing | Block scoring until engineering provides estimates |
| Value is gut-feel, not metric-backed | Arbitrary placement | Define value as specific metric impact before plotting |
| Items land on quadrant boundary | Too close to call from position alone | Use RICE or ICE for tiebreaking, not boundary proximity |

---

## Construction Checklist

- [ ] Effort estimated by engineers or builders — not product or stakeholders
- [ ] Value defined as outcome metric impact — not "important" or "requested a lot"
- [ ] Each axis has explicit low/high anchors defined before plotting
- [ ] Quadrant labels are agreed before items are placed (prevents post-hoc justification)
- [ ] Matrix is re-plotted when new information changes estimates

---

## Common Mistakes

| Mistake | Consequence |
|---|---|
| Requesters estimate effort | Effort systematically underestimated, Quick Wins quadrant overcrowded |
| Feature count used as value proxy | High-scope items ranked too high regardless of outcome |
| Treating quadrant lines as precise | Boundary items need a tiebreaker model, not matrix position alone |
| One-time plot, never revisited | Stale assumptions lock in bad priorities as context changes |
