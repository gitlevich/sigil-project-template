# Awareness

Files here are always loaded at session start. They define the ground rules — domain vocabulary and working process — that apply to every task in every session.

## Files

- **domain.md** — The project's vocabulary. Terms, their exact definitions, and language rules. Also contains a short vision summary so the agent knows the domain without reading the full vision statement. Update this when the domain grows new terms or when a term's meaning is refined.

- **process.md** — Working discipline. Task management rules, spec-as-truth principle, acceptance criteria standards, and override transparency. Update this when the team discovers a new process failure mode or corrects a recurring mistake.

## What Belongs Here

A thing belongs in awareness if it is:
- Always relevant (not task-specific or feature-specific)
- A constraint on how work is done (not what work is done)
- Something the agent would get wrong without a reminder

## What Does Not Belong Here

- Feature specs (those live in `features/`)
- Architecture decisions (those live in `docs/architecture/`)
- Session-specific state (that lives in `memory.md`)
- Task details (those live in `docs/backlog/`)
