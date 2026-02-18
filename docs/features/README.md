# Features

Each feature is a folder containing a `feature.md` that defines it through contrasts, affordances, and choices.

## Directory Structure

```
docs/features/
  observe/
    feature.md              Root feature spec
    filters/
      feature.md            Non-leaf affordance gets its own folder and spec
      category_mix/
        feature.md           Further decomposition if needed
  settings/
    feature.md
    ingest/
      feature.md
```

**Rules:**

- One folder per feature. The folder name is the feature name, lowercase, snake_case.
- Every folder has exactly one `feature.md`.
- A **non-leaf affordance** in a parent spec becomes a subfolder with its own `feature.md`. The parent links to it.
- A **leaf affordance** stays described in its parent's spec. No subfolder.
- The tree bottoms out when every affordance at the current level is a leaf — something whose name and contract are known and whose internals are not your concern.

## Feature Document Format

A feature spec has three sections:

### Contrasts

Axes of differentiation within this feature. Each contrast has two poles and a stated preference.

```
- **pole A vs. pole B** — I favor pole A. [Why this matters here.]
```

Both poles must be real temptations. If one pole has no pull, it is not a contrast — discard it.

### Affordances

Five to seven named parts of the feature. Each is either leaf or non-leaf.

```
- **Affordance Name** — what it offers attention. [Leaf / Non-leaf, link to subfolder.]
```

Affordances are capabilities, not UI components. "Ingest", not "Ingest Panel".

### Choices

How observations collapse under this feature's preferences. What questions does attention ask here, and what actions result?

## How Features Get Created

Say "add a feature." The agent enters the write_feature sigil: it inhabits the feature, narrates from inside, discovers contrasts and affordances through conversation, and writes the spec. You discover the feature together — the agent does not generate it from a description.
