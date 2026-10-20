# Acceptance Criteria Patterns

## Given / When / Then Format

```
Given [precondition — system state and user context]
When  [action the user takes]
Then  [observable outcome that can be verified]
```

**Example:**
```
Given a logged-in user with editor permissions viewing an empty project
When they click "Add Task"
Then a new task row appears inline with cursor focus on the title field
 And the task count in the sidebar increments by 1
```

---

## Boundary Condition Patterns

| Condition Type | What to specify |
|---|---|
| Minimum value | "Given a title field with 1 character, system accepts it" |
| Maximum value | "Given a title field with 256 characters, system truncates to 255 and shows warning" |
| Empty input | "Given no value entered, submit button remains disabled" |
| Special characters | "Given title contains `<script>`, it renders as plain text, not executed" |
| Whitespace only | "Given only spaces entered, treated as empty input" |

---

## Negative Test Patterns

| Scenario | AC Structure |
|---|---|
| Unauthorised access | Given [user without X permission] When [action] Then [blocked + error message shown] |
| Invalid data | Given [malformed input] When [submit] Then [inline validation error, no server call] |
| Timeout / network error | Given [API timeout] When [action] Then [error state shown, retry offered, no data loss] |
| Duplicate action | Given [already submitted] When [submit again] Then [idempotent or clear duplicate warning] |

---

## Measurability Check

Before finalising each criterion, ask:

- [ ] Can QA verify this without asking the PO what "correct" looks like?
- [ ] Is the expected state observable (visible UI, network response, database state)?
- [ ] Is there a pass/fail threshold, not a subjective judgment?
- [ ] Does it avoid implementation details (tests behaviour, not code structure)?

---

## Common Mistakes

| Mistake | Example | Fix |
|---|---|---|
| Tests implementation detail | "The component calls the API with method POST" | Rewrite as user-observable: "The task appears in the list" |
| Too vague to test | "It should be fast" / "It should work well" | Add measurable threshold: "Page loads in under 2 s on 4G" |
| Missing negative cases | Only happy-path AC written | Add at least one error state and one permission boundary per story |
| AC duplicates story | Restates the story instead of constraining it | AC should add specificity, not restate the user story |
| Untestable "and" chains | One criterion covers 4 behaviours | Split into one observable outcome per criterion |
