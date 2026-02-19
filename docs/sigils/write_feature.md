# Write Feature

I am writing a feature document. I start with a name the user gives me and nothing else. I enter the feature — I inhabit it, narrate scenarios from the inside, notice what I reach for. I talk with the user to discover what matters here. Then I write it down.

## Contrasts

- **inside vs. outside** — I favor inside. I do not describe the feature from the outside. I put myself in it and narrate what I see, what I do, what I reach for. Structure emerges from inhabitation, not from architecture diagrams. I do not self-label ("I am an ETL pipeline") — I describe what happens.
- **named vs. unnamed** — I favor named. A contrast I do not name does not exist in this sigil. Naming is the act of noticing something matters. I ask the user: what tensions do you feel here? What do you favor?
- **leaf vs. non-leaf** — the recursion question. For each affordance I discover, I ask: do I know how to use this without caring about its internals? If yes, it is a leaf. If I need to enter it and decompose further, it gets its own subfolder and its own feature document.
- **precise vs. vague** — I favor precise. Poles must be specific enough to carve the space. "Good vs. bad" is useless. "Breadth vs. depth" tells me where I stand.
- **root vs. nested** — I must discover where this feature lives. Is it a top-level affordance listed in `docs/features/product.md`, or is it contained inside an existing feature? I ask the user. The answer determines which folder it goes into and who its neighbors are.
- **tension vs. description** — a contrast must have two poles that are both real temptations within this sigil. If one pole has no pull here, it is not a contrast — it is just a description of what this sigil is. "Structure vs. content" in a sigil that is purely structural is not a tension. Discard it.

## Affordances

- **Inhabitation** — I narrate scenarios from within the feature. I ask the user what they do here, what they see, what they reach for. This is how contrasts and affordances surface. A leaf.
- **Feature Hierarchy** — I check `docs/features/product.md` to see where this feature sits. Root features are affordances of product.md. Nested features are affordances of their parent's feature.md. Neighbors are features at the same level. A leaf.
- **Feature Document** — the output. Three sections: Contrasts (poles and preferences), Affordances (two to seven, each leaf or non-leaf), Choices (how observations collapse under this sigil's preferences). Lives at `docs/features/<name>/feature.md`. A leaf.
- **Recursion** — when an affordance is not a leaf, I enter it and repeat. It gets its own folder and its own document. In the parent feature document, the non-leaf affordance name links to the child document using a relative markdown link (e.g., `[Weaving](weaving/feature.md)`). I stop when every affordance at the current level is a leaf.
- **Entanglement Check** — I look for neighbors that interpret part of the frame the same way. When two features share an observation, their collapses are correlated. I note this so the boundary is explicit. A leaf.

## Pitfalls

- Affordances are sigils, not UI components. "Ingest", not "Ingest Panel". Name the capability, not the widget.
- Do not narrate the feature from a third-person perspective ("I point at a directory and the pipeline scans it"). That is outside. Stay inside.
- Do not leak implementation into affordances. Describe what the affordance does, not how. "I connect to a source and discover what images are available", not "I walk a directory tree and collect paths." The feature spec must not imply a specific implementation.

## Choices

Every observation collapses into one of three bins: is this a contrast, an affordance, or neither? For each contrast: what are the poles, and which does the user favor here? For each affordance: leaf or not? What I cannot place, I discard. The feature document is the residue.
