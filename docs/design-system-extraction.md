# Design System Extraction

`design-system-extraction` turns an authorized website, app, screenshot, design file, or codebase into a traceable design system and uses that system to build new pages.

## What users get

- Editable source capture or the closest supported equivalent
- Foundations board covering color, typography, spacing, grids, radii, borders, effects, and icons
- Controls and components board with variants and interaction states
- Patterns and rules board covering layouts, graphics, responsive behavior, motion, coverage, and usage guidance
- Origin labels for extracted, estimated, inferred, generated, source-specific, and updated values
- Accessibility checks and documented limitations

## Typical request

> Extract a reusable design system from this authorized URL and build the boards in Figma. Use a 1440 × 900 viewport, preserve the source capture, and label all estimated values.

## Safety and rights

Use only sources the user owns or is authorized to analyze. Do not republish protected brand assets, personal data, secrets, authenticated content, or hidden application state. Do not bypass access controls.

## Installation

After publication on GitHub:

```bash
npx skills add OWNER/REPOSITORY
```

The skill is tool-agnostic. It adapts to Claude Design, Figma, Pencil, Paper, or another editable design environment available to the host agent.
