# FileABug

Triggered by: "file a bug about ...", "that's a bug, file it", "file a bug", etc.

1. Research the problem in the codebase. Read the relevant code paths.
2. Read `docs/bugs/.counter` for the next bug number. After creating the report, increment the counter and write it back.
3. Create `docs/bugs/IS_NNNNNNNN_short_summary.md` where N is zero-padded incremental, summary is 2-4 words snake_case.
4. The report contains:
   - **Status**: Open
   - **Reported**: today's date
   - **Component**: which module(s)
   - **Symptom**: what the user observes
   - **Expected behavior**: what should happen
   - **Root cause analysis**: trace the code, cite file:line, explain the failure mechanism
   - **Acceptance criteria**: concrete testable conditions that must hold when fixed. Reference existing criteria if applicable; propose new ones if not.
   - **Proposed fix**: what changes resolve it
   - **Reproduction**: minimal steps to trigger

## Closing a bug

When a bug is fixed: set **Status** to `Resolved — <one-line reason>`, then move the file to `docs/bugs/done/`.
When a bug is stale (target code no longer exists): set **Status** to `Stale — <reason>`, then move to `docs/bugs/done/`.
