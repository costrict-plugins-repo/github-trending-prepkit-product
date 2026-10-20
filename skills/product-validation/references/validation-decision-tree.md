# Validation Decision Tree

When to validate, how deeply, and which method to use.

## Confidence vs. Method Matrix

| Confidence Level | Evidence Available | Validation Method | Time Estimate |
|---|---|---|---|
| Very low — gut hunch | None | Customer problem interviews (5-8 people) | 1-2 weeks |
| Low — some anecdotal signals | 1-3 user quotes or support tickets | Survey (n=50+) + analytics review | 1 week |
| Medium — recurring pattern seen | Interview data + behavioral signals | PR/FAQ draft + stakeholder review | 3-5 days |
| High — validated problem, uncertain solution | Strong problem evidence | Prototype + moderated usability test | 1-2 weeks |
| Very high — proven need + tested solution | Multiple data sources aligned | Proceed to PRD | 0 additional days |

Rule: match validation depth to confidence gap, not to stakeholder urgency.

## Assumption Risk Matrix

| Assumption | Risk If Wrong | Cheapest Test |
|---|---|---|
| User actually has this problem | Critical | 5 problem interviews |
| Our solution addresses the problem | High | Low-fidelity prototype test |
| Users will pay our target price | High | Pricing survey or fake-door pricing page |
| Enough users exist (market size) | High | TAM/SAM/SOM calculation + comparable data |
| We can build it in the proposed timeline | Medium | Technical spike (1-3 days) |
| This doesn't cannibalize existing revenue | Medium | Revenue impact model before build |
| Users will discover and adopt without heavy support | Low-Med | Onboarding analytics on a comparable feature |

Sequence: test highest-risk assumptions first. Stop when evidence clearly supports "build" or "don't build."

## Validation Gate Checklist

Before writing any PRD:
- [ ] Problem interviewed with at least 5 target users (not internal users)
- [ ] Riskiest assumption identified and tested or explicitly accepted as risk
- [ ] Solution concept tested at low fidelity (sketch, mockup, fake door, or PR/FAQ review)
- [ ] Business case modeled (desirability + viability + feasibility all pass)
- [ ] Counter-scenario documented: what would we do if this doesn't work?

## Fake Door Tests

| Fake Door Type | What It Tests | How to Run |
|---|---|---|
| Landing page with waitlist | Is there demand for this concept? | Drive 200+ targeted visitors; measure sign-up rate |
| "Coming soon" feature CTA | Do existing users want this? | Add button in-app; measure click rate vs. baseline |
| Pricing page variant | Will users pay $X for this? | Show pricing page; measure checkout attempts |
| Concierge MVP | Does the solution work manually before building? | Do it by hand for 5-10 users; measure satisfaction |

## Common Mistakes

| Mistake | Fix |
|---|---|
| Validating easiest assumptions first | Rank by risk × reversibility, test riskiest first |
| Confusing interest with purchase intent | "Would you use it?" ≠ "Would you pay for it?" |
| Testing with colleagues or founders | Recruit target users only — insiders don't represent the market |
| Stopping after one positive interview | 5 interviews minimum; look for pattern, not confirmation |
