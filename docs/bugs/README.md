# Bugs

Open bug reports live here. Resolved or stale bugs move to `done/`.

## File Naming

```
IS_00000001_short_summary.md
```

- Number: zero-padded to 8 digits. Read from `.counter` in this directory; increment after use.
- Summary: 2-4 words, snake_case.

## Bug Report Format

```markdown
# Title

**Status:** Open
**Reported:** YYYY-MM-DD
**Component:** which module(s)

## Symptom

What the user observes.

## Expected behavior

What should happen instead.

## Root cause analysis

Trace the code path. Cite file:line. Explain the failure mechanism.

## Acceptance criteria

- [ ] Concrete testable condition
- [ ] Another condition

## Proposed fix

What changes resolve it.

## Reproduction

Minimal steps to trigger.
```

**Rules:**

- The agent researches the problem before filing — root cause analysis is required, not optional.
- When fixed: set Status to `Resolved — <reason>`, move to `done/`.
- When stale (code no longer exists): set Status to `Stale — <reason>`, move to `done/`.
