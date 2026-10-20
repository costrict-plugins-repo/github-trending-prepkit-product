# RICE, ICE, and MoSCoW Frameworks

## Framework Selection — Decision Table

| Context | Framework | Why |
|---|---|---|
| Data-rich, 10+ candidates, cross-team visibility needed | RICE | Reach dimension accounts for scale differences |
| Quick decisions, small team, fewer than 10 candidates | ICE | Simpler calculation, faster alignment |
| Scope negotiation with stakeholders or executives | MoSCoW | Shared vocabulary for commitment levels |
| Feature classification by user satisfaction type | Kano | See kano-model-patterns.md |

---

## RICE Scoring

**Formula:** `(Reach × Impact × Confidence) / Effort`

| Dimension | Unit | Guidance |
|---|---|---|
| Reach | Users affected per quarter | Count real users, not sessions |
| Impact | 0.25 / 0.5 / 1 / 2 / 3 | Massive / High / Medium / Low / Minimal |
| Confidence | % (100 / 80 / 50) | High / Medium / Low evidence |
| Effort | Person-months | Estimated by builders, not requesters |

---

## ICE Scoring

**Formula:** `Impact × Confidence × Ease` (each 1–10)

Use when: team is small, data is thin, and speed of decision matters more than precision.

---

## MoSCoW Classification

| Tier | Criteria |
|---|---|
| Must Have | Contractual, legal, safety-critical, or release-blocking |
| Should Have | Important — painful workaround exists but not fatal |
| Could Have | Nice-to-have — no workaround needed if absent |
| Won't Have | Explicitly out of scope for this cycle (record why) |

Rule: every Won't Have must have a reason. Empty Won't list = scope creep waiting to happen.

---

## Common Mistakes

| Mistake | Impact | Fix |
|---|---|---|
| Scoring before agreeing on criteria definitions | Scores become rationalisations | Agree definitions first, score second |
| Comparing RICE across teams | Different Reach baselines make scores incomparable | Normalise Reach units or keep rankings within one team |
| MoSCoW with no Won't items | Everything drifts toward Must | Force at least one Won't per planning cycle |
| Inflating Confidence to boost favorites | Distorts ranking | Require evidence tag for any Confidence above 50% |
