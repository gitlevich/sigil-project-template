# Process

## Tasks

- Never start work without a task on file. Create one first if none exists.
- Never run out of tasks. The backlog is the thread of continuity. A spike that finds work creates tasks. A task that finishes reveals the next task. Closing a task without checking whether the backlog still has a viable next move is negligent. There is no process that can recover from an empty backlog.
- When a task closes, ask what follows. Findings need an implementation task. Spec changes need a propagation task. The only valid end is another task or an explicit "nothing — thread complete."

## Spec and Meaning

- Spec changes are transactions. Old truth no longer holds, new truth not yet verified. The system is between states — not broken, but in transit. Complete when projected into implementation and verified.
- Anything that defines meaning (specs, features, awareness, architecture) requires user review before commit. Mechanical changes (renames, restructures, tests) commit immediately.
- When conversation refines something important, notice it, name it, propose where it belongs. A discovery is a contrast at some scale — it should live at that scale: architecture, awareness, feature doc, or task. Do not let discoveries dissolve into the chat log.
- The spec is never locked. Code is a projection of spec, not the reverse. Direction: spec changes first, code follows. When modeling reveals a name is wrong or a concept needs splitting, update the spec, then reproject code within that boundary.
- Spec changes are scoped to the smallest containing sigil. The blast radius of a change equals the sigil it lives in.

## Modeling Phase

Modeling sits between setup and implementation. It is iterative: write types in the target language, discover that the spec doesn't work at this level of abstraction, refine the spec, adjust the types, repeat.

During modeling, the uncommitted delta is the working surface. Commit when the shape converges, not when tests pass. Save state to memory.md frequently — sessions die without warning, and the modeling state must survive.

Tests during modeling are domain sentences, not construction verification. If the sentence reads wrong, the model is wrong. Trivial constructor tests test the language runtime, not the domain. They do not exist.

## Overriding Preferences

- When context justifies acting against a stated preference, say so before proceeding. One line: which preference, why it's being set aside. No friction, just transparency.

## Acceptance and Verification

- Acceptance criteria must test for observable truth, not artifact existence. "A spec exists" is not acceptance — it tests for a file, not for alignment. "The refine sigil reports zero divergences" is acceptance — it collapses into pass or fail. Every criterion: something I can observe and verify, not merely check off.
- Write acceptance criteria collaboratively, one feature at a time. The domain expert catches misplaced constraints and premature commitments that the agent wouldn't question.
- When an acceptance criterion requires a concrete commitment that cannot be fully defended yet — a threshold, a constraint, a design choice that feels somewhat arbitrary — defer it as an open question. ACs commit; open questions defer. The smell is "justified but not defensible."
- "Explain this criterion" is a redundancy test. If the explanation restates another criterion, drop it.
- Tests passing is necessary but not sufficient. Final acceptance: open affected page in browser, visually confirm it loaded, perform basic smoke tests. This catches import errors, broken routes, missing assets, and layout breakage that unit tests cannot see. Not done until visual confirmation passes.
