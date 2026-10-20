# Cohort Retention Patterns

Retention analysis patterns for reading, diagnosing, and acting on cohort data.

## Cohort Type Selection

| Cohort Type | Grouped By | Best For | Avoid When |
|---|---|---|---|
| Acquisition cohort | Signup date (week/month) | Tracking overall product health trends over time | Cohort sizes vary wildly (distorts comparisons) |
| Behavioral cohort | Key action completed (finished onboarding, used feature X) | Measuring impact of specific feature or flow | Action definition changes over time |
| Revenue cohort | First payment date | Unit economics, LTV, expansion revenue tracking | Free products with no revenue event |

Start with acquisition cohorts for baseline health. Switch to behavioral cohorts when diagnosing specific feature impact.

## Retention Curve Patterns

| Curve Shape | Meaning | Action |
|---|---|---|
| Flat after initial drop | Healthy — retained users stay retained | Investigate why the initial drop happens |
| Continuous gradual decline | Product-market fit problem | Run churn interviews before any feature work |
| Sudden cliff at specific day | Event-triggered churn (bug, price change, email) | Investigate that date's release/event log |
| Smile curve (dip then recovery) | Re-engagement campaign working | Measure resurrection rate and channel attribution |
| Rising curve | Improving onboarding or product | Identify what changed; preserve it |

## Retention Benchmarks

| Metric | Formula | Consumer App | B2B SaaS |
|---|---|---|---|
| D1 retention | Active day 1 / signups | 40-60% | 60-75% |
| D7 retention | Active day 7 / signups | 20-35% | 40-55% |
| D30 retention | Active day 30 / signups | 10-20% | 25-40% |
| Monthly churn | Lost users / start-of-month users | <5% | <2% |
| Net Revenue Retention | (Revenue - Churn + Expansion) / Starting Revenue | N/A | >100% |

Benchmarks are reference ranges, not universal targets. Compare against your own trend first.

## Resurrection Flow Design

For dormant users (no activity 14+ days):

1. **Identify** dormant segment — define inactivity threshold per product (14d, 30d, 60d)
2. **Segment** by last action — what were they trying to accomplish before dropping off?
3. **Message** with value reminder, not guilt — "here's what's new" not "we miss you"
4. **Offer** comeback incentive only if reactivation economics justify it
5. **Track** resurrection rate by cohort and channel — measure incrementally vs. no contact

Counter-metric: track unsubscribe/spam rate per re-engagement campaign. Aggressive campaigns damage email deliverability.

## Churn Investigation Checklist

Before building a retention feature, answer:
- [ ] At what day does churn peak? → identifies which funnel stage to fix
- [ ] Which user segments churn fastest? → personas or use cases with weak fit
- [ ] What was the last action before churn? → exit point in product flow
- [ ] What do churned users say in exit surveys? → stated reason vs. behavioral data
- [ ] Do churned users return? → if yes, what triggers resurrection?

## Common Mistakes

| Mistake | Fix |
|---|---|
| Only tracking acquisition cohorts | Add behavioral cohorts for feature impact analysis |
| Comparing cohorts of different sizes | Use percentage-based metrics, not absolute counts |
| Ignoring seasonal effects | Mark holidays, campaigns, pricing changes on cohort chart |
| No counter-metric for resurrection campaigns | Always measure spam/unsubscribe rate alongside reactivation |
| Treating average retention as representative | Segment by acquisition source, plan tier, and activation status |
