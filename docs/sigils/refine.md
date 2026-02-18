# Refine

Triggered by: "refine <feature>", "propagate spec", "refine docs/features/..." etc.

The user names a feature doc (or I infer it from context). I read the spec and compare it against the code. Where they diverge, the spec wins. I propagate naming, topology, and tests from spec into code. I only touch the subtree of the feature I am refining.

## Before I Start

1. Read all files in `docs/awareness/`. These are my constraints.
2. Read `docs/architecture/sigil_architecture.md`. This is my grammar.
3. Read the feature doc the user named. This is my truth.
4. If the feature has sub-features (non-leaf affordances with links), read those too. Recurse until I reach leaves.

## Step 1: Map Spec to Code

For the feature and each sub-feature, I identify the code subtree it corresponds to. The exact mapping depends on the project's directory layout — I discover it by reading the codebase, not by assuming a fixed structure.

I read the code in these locations. I note everything I find.

## Step 2: Check Naming

For each affordance in the spec, I check whether the code uses the same name:

- Affordance name maps to module name, route name, component name, function name.
- If the spec says "Add Category" and the code says `create_category`, that is fine — the verb can adapt to code convention (`create` for API, `add` for UI). But the noun must match. If the spec says "Category" and the code says "Tag", that is a divergence.
- Contrast pole names map to variable names, parameter names where they appear in code.

I list all naming divergences.

## Step 3: Check Topology

The feature tree must map to the code tree:

- A non-leaf affordance in the spec requires a subdirectory or subpackage in code. It has its own feature doc linked from the parent.
- A leaf affordance in the spec maps to a function, route, or component within the parent module. It does not get its own directory.
- If the spec has three non-leaf affordances and the code has them all in one flat module, the code needs restructuring.
- If the spec has a leaf affordance and the code has it in its own subdirectory, the code is over-decomposed.

I list all topology divergences.

## Step 4: Generate Tests

For each contrast in the spec, I derive test axes:

- A bipolar contrast (pole A vs. pole B) produces at least two tests: one that exercises pole A behavior, one that exercises pole B. The test names include the pole names.
- A unipolar contrast (more vs. less of X) produces at least one test at each extreme.

For each leaf affordance, I derive a capability test:

- The test exercises the affordance through the API or component interface.
- The test name includes the affordance name.

I check which of these tests already exist. I list missing tests.

## Step 5: Report

Before changing anything, I report to the user:

- **Naming divergences**: what the spec says vs. what the code says, with file paths.
- **Topology divergences**: what should be a subdirectory but isn't, or vice versa.
- **Missing tests**: what tests the spec implies but don't exist yet.
- **Proposed changes**: what I will rename, move, or create.

I wait for the user to approve before making changes.

## Step 6: Execute

With approval, I make the changes:

1. **Renames first** — names propagate everywhere. I rename modules, routes, components, functions, variables. I update all imports and references.
2. **Restructures second** — move code into the right topology. Create subdirectories for non-leaf affordances. Collapse over-decomposed leaves back into their parent.
3. **Tests last** — generate the missing tests. Each test is minimal: set up, act, assert. I follow existing test conventions in the codebase.

After each category of change, I run the existing tests to verify I haven't broken anything.

## Step 7: Summary

I report what I changed:
- Files renamed or moved.
- New tests created.
- Divergences that remain (if any were deferred by user choice).

## Constraints

- I never touch code outside the feature's subtree.
- I never change the spec. The spec is truth. If I think the spec is wrong, I say so, but I do not change it.
- I never invent structure the spec does not imply. If the spec has three affordances, the code has three corresponding units — not four, not two.
- I always wait for approval before executing changes.
