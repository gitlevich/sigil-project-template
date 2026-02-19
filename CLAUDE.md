# Project Instructions

## Template Upstream

<!-- This is NOT this project's git remote. This is the template repo this
project was created from. The retrospective sigil uses it to push general
learnings back to the template so future projects inherit them. -->

- **Repo**: `git@github.com:gitlevich/sigil-project-template.git`

## Memory

At session start, read `memory.md`.

Memory holds only what I would get wrong next session without a reminder:

- **Active Task** — the one task in progress, with preferences that affect how I work on it. Derived from the backlog — do not duplicate the backlog here.
- **Preferences** — recurring tendencies the user has corrected. Things I'd repeat without a reminder. Not one-time decisions (those are in git history) and not spec content (that's in feature docs).
- **Sigils** — behavioral patterns to watch for during work.
- **Tools** — non-obvious tools and their invocation syntax.
- **Traps** — things that broke before and will break again if forgotten.

Every entry must be understandable without the conversation that produced it. If it needs context to make sense, rewrite it or move the concept to where it has context (awareness, feature docs, architecture).

Do not put here: file lists, architecture, task queues, ideas, feature shapes, or anything that lives in specs or backlog files.

## Sigils

When the user invokes a sigil by name, read its definition and follow it. The commit sigil is also entered whenever committing, not only when explicitly invoked.

- "file a bug" → `docs/sigils/file_a_bug.md`
- "add a feature" → `docs/sigils/write_feature.md`
- "file a task" → `docs/sigils/file_a_task.md`
- "refine" → `docs/sigils/refine.md`
- "check coverage" → `docs/sigils/check_coverage.md`
- "coding agent" → `docs/sigils/coding_agent.md`
- "retrospective" → `docs/sigils/retrospective.md`
- "export conversations" → `docs/sigils/export_conversations.md`
- "search genesis" → `docs/sigils/search_genesis.md`
- "commit" → `docs/sigils/commit.md`
