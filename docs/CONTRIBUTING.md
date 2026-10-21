# Contributing

Contributions should improve extraction accuracy, portability, safety, or the quality of the resulting design-system handoff.

## Before opening a pull request

1. Keep `SKILL.md` tool-agnostic. Name a tool only when describing an optional capability or fallback.
2. Preserve the origin-label model and visible source-to-system comparison.
3. Do not add instructions that bypass authentication, paywalls, robots restrictions, licenses, or user consent.
4. Use realistic examples without third-party secrets, private data, or protected assets.
5. Confirm the YAML frontmatter contains a valid `name` and `description`.
6. Run `npx skills add . --list` and verify `design-system-extraction` is detected.

## Pull requests

Keep changes focused. Explain the problem, the behavior change, and how you validated it. Update `docs/CHANGELOG.md` for user-visible changes.
