# Project Name

> Replace this with your project name and delete this line.

## For the Human

This project is structured so an AI coding agent can pick up where it left off across sessions. Everything the agent needs to behave correctly is on disk, not in chat history.

### What's Where

```
vision.md              Your vision statement. The agent reads this to understand
                       what the project is and what it is not.

memory.md              Session memory. The agent writes here at the end of each
                       session. You rarely touch this — just read it if you want
                       to see what the agent thinks is in progress.

CLAUDE.md              Agent instructions. Tells Claude where to find everything,
                       which sigils exist, and how memory works. Edit this when
                       you add new sigils or change project conventions.

features/              Feature specs. Each feature is a folder with a feature.md.
                       Nested features get subfolders. This is the source of truth
                       for what the application does.

docs/
  awareness/           Domain terms and working process rules. Always loaded.
    domain.md          Vocabulary, language rules, vision summary.
    process.md         Task discipline, spec-as-truth, acceptance criteria.

  architecture/        Structural documents that define how sigils compose.
    sigil_architecture.md   The foundational framework.

  sigils/              Behavioral patterns the agent enters when triggered.
                       "commit", "file a task", "add a feature", etc.

  backlog/             Active tasks. Closed tasks move to done/.
  bugs/                Open bug reports. Closed bugs move to done/.
```

### How to Start a Session

Say "coding agent" and the agent enters its working sigil — it reads awareness, memory, and backlog, then picks up the highest priority task.

### How to Add Work

- "file a task" — creates a task in the backlog
- "add a feature" — inhabits a feature and writes its spec with you
- "file a bug" — researches and files a bug report
- "refine \<feature\>" — propagates a feature spec into code
- "check coverage" — measures test coverage
- "commit" — reviews, stages, and commits with memory hygiene

## For the Agent

When you open a session in this project, read in this order:

1. `CLAUDE.md` — your instructions and sigil registry
2. `docs/awareness/domain.md` — vocabulary and language rules
3. `docs/awareness/process.md` — working discipline
4. `memory.md` — what happened last session

Do not start work without a task. If the user asks for something and no task exists, create one first.

When the user invokes a sigil by name, read its definition from `docs/sigils/` and follow it. The commit sigil activates on every commit, not only when explicitly named.

When you discover something worth keeping — a new preference, a trap, a process correction — propose where it belongs: awareness, memory, a sigil update, or a task. Do not let it dissolve into the conversation.

Ask the user for:
- The **vision statement** if `vision.md` is empty. You need to understand what the project is before you can work on it.
- **Feature priorities** if the backlog is empty. You cannot pick a task if none exist.
- **Approval** before committing any change to meaning (specs, awareness, architecture). Mechanical changes (renames, tests, code implementing an existing spec) you can commit without asking.
