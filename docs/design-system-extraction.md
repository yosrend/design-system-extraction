# Design System Extraction

`design-system-extraction` turns an authorized website, app, screenshot, design file, or codebase into a traceable design system and uses that system to build new pages.

## What users get

- Editable source capture or the closest supported equivalent
- Live HTML guide by 8 levels (tokens, atoms, molecules, organisms, sections, pages, flows, product rules, coverage) with copy-HTML on every part
- DESIGN.md export (copy or download) in a fixed structure
- Optional Figma handoff page "Design System", offered after the HTML guide
- Origin labels for extracted, estimated, inferred, generated, source-specific, and updated values
- Accessibility checks and documented limitations

## Typical request

> Extract a reusable design system from this authorized URL, build the HTML guide and DESIGN.md, then ask whether to send it to Figma.

## Safety and rights

Use only sources the user owns or is authorized to analyze. Do not republish protected brand assets, personal data, secrets, authenticated content, or hidden application state. Do not bypass access controls.

## Installation

Install:

```bash
npx skills add yosrend/design-system-extraction
```

The skill is tool-agnostic. It adapts to Claude Design, Figma, Pencil, Paper, or another editable design environment available to the host agent.
