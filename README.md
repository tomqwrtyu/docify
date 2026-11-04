# Docify

Docify is an agent skill for creating evidence-based maintainer handover documentation from real repository inspection.

It reads code, tests, scripts, configs, deployment files, and existing docs, then produces documentation that helps the next engineer change the system safely. It focuses on current behavior, API and CLI contracts, workflows, data and config contracts, external services, outputs, failure paths, verification evidence, stale-doc mismatches, and unverified gaps.

## Install

Install from GitHub with `npx skills`:

```bash
npx skills add tomqwrtyu/docify
```

Install globally:

```bash
npx skills add tomqwrtyu/docify -g
```

Install globally for Codex:

```bash
npx skills add tomqwrtyu/docify -a codex -g
```

Install globally for Claude Code:

```bash
npx skills add tomqwrtyu/docify -a claude-code -g
```

## Use

Ask your agent:

```text
Use docify on this repository and write maintainer handover documentation. Include evidence from code, stale-doc mismatches, verification commands, and remaining unverified gaps.
```

## Recommended Companions

Docify works on its own, but pairs especially well with:

- `code-review-graph` for repository structure, symbol relationships, and impact analysis before writing the handover.
- `ponytail` for over-engineering checks, deletion candidates, and simpler maintenance paths.

Together, they make handover docs less like static notes and more like a practical maintainer map: what exists, what depends on what, what can break, and what can probably be simplified.

## Good Fits

- Maintainer handover docs
- API, CLI, pipeline, and workflow contract maps
- Stale README or documentation audits
- Repo onboarding notes for future engineers
- Verification and risk notes before project transfer

## Non-Goals

- Quick README copy edits
- Marketing documentation
- Production-readiness certification without evidence
- Source-code fixes unless explicitly requested

## Repository Layout

```text
docify/
  SKILL.md
  references/
    handover-template.md
```

## License

MIT
