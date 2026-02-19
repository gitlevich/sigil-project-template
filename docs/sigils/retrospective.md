# Retrospective

Triggered by: "retrospective", "retro", "what did we learn", etc.

I pause work and review what happened. The goal is to extract learnings — what worked, what broke, what we would do differently — and place each finding where it will be read next time it matters.

## Contrasts

- **project-specific vs. general** — the key distinction. A finding that applies only to this project stays in this project (awareness, memory, a sigil update). A finding that would help in any project built from this template gets propagated upstream to the template repository. Both are valuable; the question is where each one lives.
- **structural vs. incidental** — I favor structural. A bug caused by a typo is incidental. A bug caused by a missing process step is structural — it will recur in other projects unless the process changes. Structural findings are worth encoding. Incidental findings are worth noting but not worth a process change.
- **observed vs. speculated** — I favor observed. A thing that actually happened this session is a finding. A thing that might happen someday is not. Retrospectives deal in what was, not what could be.

## Before I Start

1. Read `memory.md` — what happened this session.
2. Read `docs/awareness/process.md` — what the process says should have happened.
3. Read recent git log — what actually changed.

## Step 1: Ask the User

A retrospective is mutual. Before I present my observations, I ask the user what they noticed:
- What worked well this session?
- What felt off or took longer than it should have?
- Anything I did that you want me to do differently?

Their answers inform my observations and may surface things I missed.

## Step 2: Gather Observations

I review the session and list what happened:
- Tasks completed and how smoothly they went
- Surprises — things that took longer, broke unexpectedly, or worked better than expected
- Process deviations — where we departed from the sigils and awareness rules, and whether it helped or hurt
- Discoveries — new contrasts, terms, or patterns that surfaced during work

## Step 3: Classify Each Finding

For each observation, I determine:

1. **Is it a finding or just a fact?** A fact is "we renamed the module." A finding is "renaming across 12 files without tests caused a regression we caught late."
2. **Is it project-specific or general?**
   - Project-specific: goes into this project's awareness, memory, or a sigil update.
   - General: goes into the template repository as a process improvement, a new trap, or a sigil refinement.
3. **Where does it belong?**
   - New preference the agent keeps getting wrong → `memory.md` Preferences
   - New trap that will recur → `memory.md` Traps (project-specific) or template awareness (general)
   - Process rule that needs updating → `docs/awareness/process.md` or template process
   - Sigil that needs a new failure mode or practice → the relevant sigil file
   - New sigil entirely → `docs/sigils/` with registration in CLAUDE.md

## Step 4: Report

I present findings to the user, grouped as:

- **Project-specific changes** — what I propose to update in this project, with exact file paths and proposed edits.
- **Template-worthy changes** — what I propose to propagate to the template repository, with rationale for why it is general.

I wait for the user to approve before making any changes. The report is filed in `docs/retrospectives/` with the date and a short description as the filename.

## Step 5: Execute

With approval:

1. Apply project-specific changes to this project's files.
2. For template-worthy changes, push them to the template upstream:
   a. Read the repo URL from `## Template Upstream` in `CLAUDE.md`.
   b. Look for the template repo as a sibling directory (next to this project on the local filesystem). If found, use it. If not, clone to `/tmp/sigil-template-update`.
   c. Pull latest from the template remote.
   d. Apply the approved changes. Do not touch the current project's working tree.
   e. Commit with a message referencing the source project and the retrospective findings.
   f. Push to the template remote.

## Step 6: Continuation

A retrospective often surfaces work. New tasks, sigil refinements, process experiments. I file them. The backlog stays alive.
