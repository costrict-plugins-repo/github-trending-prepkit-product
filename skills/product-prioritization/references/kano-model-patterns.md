# Kano Model Patterns

## Feature Categories

| Category | Absent | Present | Example |
|---|---|---|---|
| Must-Be | Dissatisfied | Neutral (never delights) | Login works, data saves reliably |
| One-Dimensional | Dissatisfied | Satisfied (linear) | Speed, storage, response time |
| Attractive | Neutral (OK) | Delighted (unexpected) | Smart defaults, surprise UX touch |
| Indifferent | Neutral | Neutral | Feature nobody uses either way |
| Reverse | Satisfied | Dissatisfied | Power-user shortcut that confuses novices |

---

## Survey Question Pair Format

Ask both questions per feature. Never ask only one.

- **Functional:** "How would you feel if [feature] existed?"
- **Dysfunctional:** "How would you feel if [feature] did NOT exist?"

Answer scale: Like it / Expect it / Neutral / Live with it / Dislike it

Map the pair to a category using the standard Kano evaluation table.

---

## Category Shift Over Time

Categories are not fixed. Market maturation moves features leftward:

```
Attractive → One-Dimensional → Must-Be
(as competitors copy and users expect it)
```

Signal: when users stop mentioning a feature as a reason to choose you, it has likely become Must-Be.

---

## When to Use Kano

- Deciding which features to invest in next
- Distinguishing "delighters" from "table stakes" before roadmap planning
- Detecting Reverse features before they ship and cause churn

---

## Common Mistakes

| Mistake | Why It Fails | Fix |
|---|---|---|
| Classifying without user data | Your excitement ≠ user satisfaction | Run survey with target segment, minimum 20 responses |
| Assuming Attractive stays Attractive | Competitors copy; market expectations rise | Re-run Kano survey annually or after major competitor moves |
| Ignoring Reverse features | Ships and causes active dissatisfaction | Always check Reverse column in your survey results |
| Using Kano for internal tools | Satisfaction model assumes end-user choice | Use RICE or MoSCoW for forced-use internal tooling |
