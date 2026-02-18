# FileATask

Triggered by: "file a task", "make a task for ...", "create a task", etc.

## Preferences

- **Incremental numbering** — read `docs/backlog/.counter` for the next number, zero-pad to 8 digits. After creating the task, increment the counter and write it back.
- **State in the filename** — `TASK_NNNNNNNN_short_summary_STATE.md`. State is IDEA, TODO, WIP, or DONE. When state changes, rename the file suffix and update the internal Status field.
- **Done means moved** — when a task reaches DONE, it moves to `docs/backlog/done/`. Done tasks never stay in the backlog root.
- **Structure over decoration** — every task has: Title, Status, Description (what and why), Scope (docs/backend/frontend/architecture), Acceptance Criteria (observable conditions), Dependencies (if any).
- **Infer state from context** — if the user doesn't specify, choose the state that fits: rough idea is IDEA, defined enough to pick up is TODO.
