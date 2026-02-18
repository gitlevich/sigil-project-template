# Backlog

Active tasks live here. Completed tasks move to `done/`.

## File Naming

```
TASK_00000001_short_summary_STATE.md
```

- Number: zero-padded to 8 digits. Read from `.counter` in this directory; increment after use.
- Summary: 2-4 words, snake_case.
- State: `IDEA`, `TODO`, `WIP`, or `DONE`.

When state changes, rename the file suffix and update the internal Status field.

## Task Format

```markdown
# Title

**Status:** TODO
**Scope:** backend / frontend / docs / architecture
**Dependencies:** TASK_NNNNNNNN (if any)

## Description

What needs to happen and why.

## Acceptance Criteria

- [ ] Observable condition that can be verified
- [ ] Another observable condition
```

**Rules:**

- Acceptance criteria test for observable truth, not artifact existence. "The API returns 200 with the expected payload" — not "an API endpoint exists."
- State meanings: **IDEA** = rough, needs refinement before work. **TODO** = defined enough to pick up. **WIP** = someone is actively working on it. **DONE** = all acceptance criteria pass, task moves to `done/`.
- The backlog must never go empty. When a task closes, the agent asks what follows.
