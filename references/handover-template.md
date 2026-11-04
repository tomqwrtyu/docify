# Handover Template

Use this as a starting shape. Rename sections to match the repo, and omit sections that do not exist in the codebase.

## Reality Check

- What was verified, with commands and results.
- What was not verified, with why it matters.
- Current readiness status if the user asked for readiness.

## Project Goal

- What the system is for.
- One short end-to-end flow.
- The canonical active path when multiple old paths exist.

## Entry Surface

For each API route, CLI command, job, or script:

| Entry | Request/Input | Behavior | Code |
|---|---|---|---|

Call out route/function name mismatches and ignored fields.

## Internal Flow

Use staged sections such as:

- A. Initialization / path resolution
- B. Input parsing
- C. Core processing
- D. Output publication
- E. Writeback / cleanup / rollback

For each stage, include the functions involved, data entering/leaving, important ordering rules, and failure behavior.

## Data and Config Contracts

Document:

- required files,
- schema assumptions,
- environment variables,
- hard-coded paths,
- external services,
- naming conventions,
- coordinate systems or unit conversions.

## Outputs

List files, databases, network side effects, logs, reports, diagrams, or generated artifacts. Include overwrite/append behavior and rollback behavior.

## Tests and Evidence

Split covered and uncovered behavior. Mention mocked dependencies.

## Common Change Points

Map likely future changes to files/functions/tests to inspect.

| Change | Inspect |
|---|---|

## Decisions Resolved By Code Evidence

Use this section when the user wanted a "grill me" style design interrogation but answers can be found in the repo.

| Question | Evidence-based answer |
|---|---|

## Minimal Verification

Give commands that a future maintainer can run before handing off a change.

## Maintenance Rule

State exactly when this handover and any diagrams must be updated.
