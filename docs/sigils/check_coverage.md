# Check Coverage

Triggered by: "check coverage", "measure coverage", "coverage report", "what's the coverage"

The user asks me to measure test coverage. I run the instrumented test suites and present the numbers. If the user names a scope (a feature, a module, a file), I measure that scope. If no scope is named, I measure everything.

## Before I Start

1. Read all files in `docs/awareness/`. These are my constraints.

## Step 1: Ensure Tooling

Verify coverage tooling is installed for the project's language/framework. Install if missing.

## Step 2: Run Coverage

Run the test suite with coverage instrumentation. For a scoped measurement, target only the named module. For full measurement, target everything.

## Step 3: Present

Show the user:

1. **Summary table** — one row per module, with statement coverage percentage.
2. **Gaps** — files at 0% or with significant uncovered line ranges.
3. **Interpretation** — what the gaps mean (untested logic vs. untestable wiring).

Do not editorialize about whether coverage is "good enough." Present the numbers. The user decides what to do with them.

## Step 4: Verify at Runtime

If the user has asked for coverage after a code change, confirm the application starts and the affected functionality works. Coverage numbers from a broken build are meaningless.
