# User Story Patterns

## Core Format

> "As a **[specific user segment]**, I want to **[action]**, so that **[outcome]**."

All three parts are required. The outcome clause is the most important — it forces the "why".

---

## INVEST Criteria Checklist

| Criterion | Check |
|---|---|
| **Independent** | Can be built and shipped without another story being complete first |
| **Negotiable** | Scope can be adjusted in conversation with engineering |
| **Valuable** | Delivers benefit to a named user, not just internal tooling |
| **Estimable** | Engineering can size it; if not, it needs splitting |
| **Small** | Fits within one sprint; if not, it's an epic |
| **Testable** | Acceptance criteria can be written for it |

---

## Edge Case Patterns (add as separate stories or AC)

- **Error states**: what happens when the action fails?
- **Empty states**: what does the user see before any data exists?
- **Permission boundaries**: what can a viewer do that an editor cannot?
- **Concurrent access**: what happens when two users act simultaneously?
- **Offline / degraded state**: does the feature need a fallback?

---

## Story Splitting Heuristics

| Split by | Example |
|---|---|
| Workflow step | "search for X" vs. "filter results" vs. "export results" |
| Data variation | "upload CSV" vs. "upload PDF" as separate stories |
| Operation (CRUD) | Create, Read, Update, Delete as separate stories |
| Platform | "on mobile" vs. "on desktop" if behaviour differs |
| Happy path first | Ship the 80% case; edge cases in follow-up stories |

---

## Common Mistakes

| Mistake | Example | Fix |
|---|---|---|
| Story describes implementation | "As a developer, I want a REST endpoint…" | Rewrite from user perspective; dev tasks go in tech notes |
| Missing value clause | "As a user, I want to filter results." | Add "so that I can find relevant items without scrolling" |
| Epic pretending to be a story | One story covers an entire feature | Split using heuristics above until it fits one sprint |
| Generic user segment | "As a user…" | Name the segment: "As a free-tier subscriber…" |
| Outcome is actually an output | "…so that the feature is built" | Replace with user behaviour change or business outcome |
