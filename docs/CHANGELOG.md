# Changelog

All notable user-facing changes are documented here.

## 2.0.0 — 2026-11-26

- Reorganized the system into an 8-level hierarchy plus coverage (00 Source capture → 09 Coverage) with A/M/O/S/T/J codes shared by HTML, DESIGN.md and Figma.
- Made the Live HTML guide the default endpoint: copy icon on every part, Copy CSS, Copy/Download DESIGN.md.
- Added Step 3c: after HTML, ask whether to send the system to Figma; if not, the skill ends at HTML + DESIGN.md.
- Added references/html-guide.md, references/design-md.md and references/figma-handoff.md (one "Design System" page, a Section per level, variables, component sets, instance-only composition, coverage Section, gates, Free-plan and plugin-bridge pitfalls).
- Added section-screenshot capture, Figma failure modes, and updated the final response contract.

## Unreleased (pre-2.0)

- Added Step 2b, part decomposition: region segmentation, per-component anatomy tables, nesting trees, extraction paths per source type, part-level states, and overlay verification against the capture.
- Added anatomy specimens, part-level coverage, and new failure modes for unreadable or drifting parts.
- Added Step 2c, media and visual treatment: media inventory, treatment tables for images, photos, video, thumbnails, avatars and illustrations, pattern and texture specs, a testable visual style summary, and placeholder-media verification.
- Added Layout, Effects and Media rows to the part anatomy table, media specimens on board 03, and media counts in the coverage matrix.
- Expanded the skill page with trigger guidance, exclusions, deliverables, minimum inputs, source decisions, operating principles, failure recovery, handoff requirements, and example requests.
- Replaced the unavailable dynamic install-count badge with a reliable skills.sh install badge.
- Added explicit installation commands for Codex, Claude Code, Cursor, Windsurf, GitHub Copilot, and all detected agents.

## 1.0.0 — 2026-10-21

- Published the complete extraction and build workflow.
- Added tool-agnostic compatibility and editable-capture fallbacks.
- Added provenance labels, coverage accounting, accessibility validation, and brand boundaries.
- Added responsible-use requirements for authorization, privacy, and source rights.
- Added installation guidance, examples, contribution guidance, security policy, and MIT license.
