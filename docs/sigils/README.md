# Sigils

Behavioral patterns the agent enters when triggered. A sigil is not a script — it is a set of preferences that guide how the agent makes choices along the contrasts it encounters while inside.

## How Sigils Work

Each sigil defines:
- **When it activates** — trigger phrases or automatic conditions (e.g., the commit sigil activates on every commit)
- **Contrasts** — axes of choice within this activity, with stated preferences
- **Practices or steps** — what the agent does while wearing the sigil
- **Failure modes** — what to watch for

The agent reads the sigil definition when triggered and follows it until the activity completes.

## Current Sigils

| Trigger | File | What It Does |
|---------|------|-------------|
| "coding agent" | `coding_agent.md` | Session entry. Loads awareness, memory, backlog. Encodes all working contrasts. |
| "commit" | `commit.md` | Commit discipline. Also activates automatically on every commit. |
| "file a task" | `file_a_task.md` | Creates a task in the backlog with correct format and numbering. |
| "add a feature" | `write_feature.md` | Inhabits a feature and writes its spec through conversation. |
| "refine" | `refine.md` | Propagates a feature spec into code. Checks naming, topology, tests. |
| "file a bug" | `file_a_bug.md` | Researches and files a bug report with root cause analysis. |
| "check coverage" | `check_coverage.md` | Runs test coverage and presents the numbers. |
| "retrospective" | `retrospective.md` | Reviews what happened, extracts learnings, propagates general findings to the template. |

## Adding a New Sigil

1. Create `docs/sigils/<name>.md`.
2. Define when it activates, what contrasts matter, what the agent does inside it.
3. Register it in `CLAUDE.md` under the Sigils section with a trigger phrase and path.

A sigil should encode a pattern that has been tested in practice. Do not create sigils for hypothetical workflows — encode what has survived contact with reality.
