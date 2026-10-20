# UX Measurement Frameworks

Companion reference to `product-metrics-analysis`. Covers the UX quality layer that sits alongside business-outcome metrics (North Star, AARRR, cohort retention).

---

## Why UX Quality Metrics Matter

Business metrics measure outcomes at the product level. They do not distinguish between outcomes achieved because users found genuine value and outcomes achieved because users were coerced, confused, or locked in. A product can grow North Star numbers while quietly degrading the user experience — until it cannot. UX quality metrics provide the early signal that business metrics lag on.

**The practical test:** if your metrics could stay green while making the product harder and more stressful to use, you need a UX quality layer.

---

## HEART Framework

Developed by Google (Kerry Rodden et al., 2010) to apply behavioral and attitudinal measurement at product scale.

**Five categories:**

| Category | What it measures | Example signal |
|---|---|---|
| **Happiness** | Attitudinal satisfaction — how users feel about the product | CSAT score, NPS, in-app rating |
| **Engagement** | Depth and frequency of interaction with core features | Sessions per week, features used per session |
| **Adoption** | Uptake of new features or new users completing onboarding | % of active users who have used Feature X; Day-7 activation rate |
| **Retention** | Whether users continue using the product over time | 30-day retention, churn rate |
| **Task success** | Whether users can complete key tasks without error or excessive effort | Task completion rate, error rate, time-on-task |

**WHY this structure matters:** the five categories cover attitudinal and behavioral signals at different timescales. A product with high Engagement but low Task success signals users are spending effort but not accomplishing goals — often a friction or discoverability problem. A product with high Happiness but low Adoption of a new feature signals the feature is not findable or compelling enough to try.

**HOW — Goals-Signals-Metrics (GSM) process:**

For each HEART category relevant to your product:

1. **Goal**: state what you want to achieve in this category in user terms. Example: "Users can complete their first export task without abandoning or asking for help."
2. **Signal**: identify an observable user behavior that would indicate progress toward the goal. Example: "User reaches the export confirmation screen and confirms."
3. **Metric**: define a trackable number. Example: "% of users who initiate an export and reach confirmation / 7-day window."

Not all five HEART categories are mandatory for every initiative. Select the categories most relevant to the problem space and define GSM for those.

**Integration with existing metric tools:** HEART does not replace North Star or AARRR. Use HEART metrics as a UX quality layer tracked alongside the primary business metric. A counter-metric violation (e.g., rising engagement without rising task success) may surface first in HEART before it appears in the North Star.

---

## Task Completion Rate

**WHY it matters:** the most direct behavioral measure of whether a design works. Attitudinal measures (satisfaction surveys) can mask operability problems because users do not always connect their frustration to the product design. Task completion rate makes operability failures visible in a number.

**HOW to measure:**

- Define the task clearly and in user terms (not interface terms). "Complete a purchase" not "click the Buy button."
- Observe a representative sample attempting the task without assistance.
- Record: completed without error / completed with error or recovery / abandoned.
- Report completion rate as a percentage; report error and abandonment rates separately.
- Establish a baseline on the current design before testing a redesign.

**Threshold guidance:** Industry benchmarking (MeasuringU) indicates that the average task completion rate across usability studies is approximately 78%. Tasks falling significantly below this average warrant investigation. For critical tasks (e.g., checkout, account recovery, safety-related flows), target materially higher completion rates — the 78% figure is a descriptive average, not a quality bar for high-stakes flows.

---

## System Usability Scale (SUS)

**WHY it matters:** SUS provides a single perceived-usability score derived from a 10-item questionnaire that can be administered quickly after any usability test session. It allows comparison across products, features, and releases without custom survey design.

**HOW to use:**

1. Administer the 10 SUS items immediately after the test session while the experience is fresh.
2. Score using the standard algorithm (odd items: score - 1; even items: 5 - score; sum × 2.5).
3. Interpret: scores above 68 are above average; scores above 80 are "good"; scores below 51 indicate significant usability problems.

**Integration:** SUS captures perceived usability (a Happiness signal in HEART terms). Use it alongside task completion rate (a Task success signal). A product with a high SUS score but low task completion rate is likely being evaluated charitably by users who do not recognize the design as the source of their struggle — a warning sign worth investigating.

---

## Pairing UX Quality Metrics with Business Metrics

| Business metric | Paired UX quality check | What divergence signals |
|---|---|---|
| DAU / MAU growth | Task success rate, Happiness | Growth via confusion or lock-in, not value |
| Engagement (sessions, time-in-app) | Task success rate, error rate | Engagement from thrashing, not value generation |
| Retention | SUS score trend, CSAT | Retention from switching cost, not satisfaction |
| Activation rate | Day-1 task completion rate | Activation steps too hard; users guess through |

---

## Sources

- S10: NNGroup UX Research Methods — attitudinal/behavioral spectrum; task-success rate as behavioral measurement.
- S04: NNGroup Usability Testing 101 — task completion rate and think-aloud protocol as primary UX quality measurement methods.
- Google HEART framework: Kerry Rodden, Hilary Hutchinson, Xin Fu, "Measuring the User Experience on a Large Scale: User-Centered Metrics for Web Applications," CHI 2010.
