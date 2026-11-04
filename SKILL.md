---
name: docify
description: Create evidence-based repository handover documentation after deep code review, including API/workflow contracts, maintenance notes, verification evidence, and optional diagrams. Use when asked to document a repo for future maintainers; not for quick README copy edits.
---

# Docify

Use this skill when the user wants a repository, pipeline, API, or session turned into durable maintainer documentation. The output should help the next engineer change the code safely.

The core stance is evidence over claims: read the code, tests, scripts, and existing docs; cross-check them; document mismatches and uncertainty plainly. Do not certify production readiness unless the verification evidence is actually strong. If the user asks not to be questioned, resolve decisions by exploring the codebase instead.

## Workflow

1. Read project instructions first, including `AGENTS.md` and any referenced files.
2. Inventory the repo with fast file search, then inspect entrypoints, tests, configs, scripts, deployment files, and existing docs.
3. Build a maintainer map: API/CLI surface, internal stages, data/config contracts, external services, outputs, failure paths, and common change points.
4. Cross-check README or old notes against code. Call out stale docs, route/name mismatches, ignored fields, fallbacks, and untested behavior.
5. Write or update a handover document. If the structure is not obvious, use `references/handover-template.md`.
6. Add or update `AGENTS.md` so future changes are required to keep the handover current. Scope the rule to real contract changes, not every typo.
7. If the user requested diagrams or the workflow is complex enough to need one, use an available diagram workflow such as archify and report validation separately from visual review.
8. Verify the result with the smallest meaningful checks: tests, syntax/compile, encoding, doc links, and diagram validation when relevant.
9. Final response should list changed files, evidence collected, and remaining unverified gaps.

## Documentation Rules

- Prefer precise code references and current behavior over aspirational design.
- Keep "known", "inferred", and "untested" separate.
- Document behavior-changing fallbacks instead of hiding them as implementation details.
- When tests pass only because dependencies are stubbed, say that.
- When a command cannot run because the environment lacks a dependency, record the dependency gap rather than treating it as a product failure.
- Do not modify source code while documenting unless the user explicitly requested fixes or the doc maintenance file itself needs an update.
- Preserve encoding. For mixed-language repos, verify UTF-8/no BOM before and after edits when local instructions require it.

## Optional Diagram Handling

Create a diagram only when requested, already implied by the task, or clearly useful for a complex handover. Keep it evidence-based and sparse: one main path, important side branches, and no invented infrastructure.

Report three claims separately:

- deterministic artifact validation,
- browser/viewport evidence,
- human/perceptual review.

If browser evidence cannot be collected, say why.
