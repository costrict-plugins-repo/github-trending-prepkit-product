# PRD Structure Checklist

## Section-by-Section Completeness Check

### Must-Have Sections

**Problem Statement**
- [ ] Written in user language, not internal terminology
- [ ] States who experiences the problem and in what context
- [ ] Not a disguised solution ("users need a dashboard" is a solution)
- [ ] Frequency and severity are indicated

**Users**
- [ ] Named segments with evidence (quotes, research, data)
- [ ] Not "all users" or "enterprise customers" without specifics
- [ ] Primary vs. secondary users distinguished if relevant

**JTBD**
- [ ] Functional job stated: what they're trying to accomplish
- [ ] Emotional job stated: how they want to feel
- [ ] Phrased in user language, not product language

**Success Metrics**
- [ ] At least one primary metric (outcome-based, not output-based)
- [ ] Baseline exists (current state measured or estimated)
- [ ] Target defined (with timeframe)
- [ ] Counter-metric included (guard against gaming the primary)

**Scope**
- [ ] In-scope items listed explicitly
- [ ] Non-goals listed explicitly (at least 2–3)
- [ ] Out-of-scope items include rationale or "not now"

**Dependencies**
- [ ] Upstream inputs listed (what must exist before work starts)
- [ ] Cross-team dependencies named (team + contact)
- [ ] External blockers noted (APIs, compliance, infrastructure)

### Recommended Sections

**User Stories**
- [ ] INVEST criteria met (see user-story-patterns.md)
- [ ] Each story maps to a named user segment

**Acceptance Criteria**
- [ ] Given / When / Then format (see acceptance-criteria-patterns.md)
- [ ] QA can verify without asking PO

**Open Questions**
- [ ] Lists unresolved decisions with owner and due date

---

## Common Mistakes

| Mistake | Consequence | Fix |
|---|---|---|
| PRD without a settled problem statement | Engineering builds the wrong thing | Block PRD until discovery is complete |
| Scope without non-goals | Stakeholders assume everything is in scope | List at least 3 explicit non-goals |
| Success metrics without baselines | Can't tell if the needle moved | Pull current metric before writing target |
| Metrics that measure output not outcome | Shipping features ≠ user value | Replace "launch X" with "users doing Y increases by Z%" |
| Dependencies left as "TBD" | Surprise blockers during sprint | Force a named owner for every dependency |
