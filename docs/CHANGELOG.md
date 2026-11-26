# Changelog

All notable user-facing changes are documented here.

## Unreleased

- HTML-first workflow: Phase A always delivers a Live HTML guide (8 levels + 09 Coverage audit) and a DESIGN.md generated from it; a handoff gate then asks whether to send the system to Figma or another design tool, otherwise the skill ends at HTML.
- Copy icon on every part of the guide: swatches (CSS variable), type rows (HTML), tables (Markdown), components (HTML and MD), screenshots, per-level and full DESIGN.md.
- DESIGN.md export section with file tree and live preview, saved next to the guide.
- Figma handoff structure: one `Design System` page with an Index and Sections 00 Source capture to 09 Coverage, Coverage as its own Section; fits Figma Free's 3-page limit.
- Capture notes for hosted builders blocked by the container proxy (use the user's Chrome) and figma-console Desktop Bridge pitfalls.
- Merged the 8-level hierarchy, staged level gates and visual QA into the published skill alongside Steps 2b and 2c.
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
