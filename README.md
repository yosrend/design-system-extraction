# Design System Extraction

Turn an authorized website, app, screenshot, design file, or codebase into a reusable, traceable design system—then build new pages from it.

[![skills.sh](https://skills.sh/b/yosrend/design-system-extraction)](https://skills.sh/yosrend/design-system-extraction)

## Why this skill

Most extraction workflows stop at a token list. This skill requires a visible, editable source capture; production-density specimen boards; traceable origins for every value; coverage accounting; accessibility checks; and a feedback loop that keeps the design system synchronized with new pages.

## What it produces

- Editable source capture or the closest supported equivalent
- Foundations: color, typography, spacing, grid, radii, borders, effects, and icons
- Controls and components with variants and interaction states
- Patterns, graphics, responsive behavior, motion, coverage, and usage rules
- Origin labels for extracted, estimated, inferred, generated, source-specific, and updated values
- Accessibility checks, source provenance, and documented limitations

## Install

```bash
npx skills add yosrend/design-system-extraction
```

List the skill without installing it:

```bash
npx skills add yosrend/design-system-extraction --list
```

## Supported sources

| Source | Fidelity | Handling |
| --- | --- | --- |
| Live URL | Exact where inspectable | Capture editable DOM/CSS and real assets |
| Design file or HTML import | Exact | Read editable node properties directly |
| HTML, CSS, JSX, or Tailwind | Exact | Render as editable HTML artboards |
| Screenshot or image | Estimated | Rebuild visually and label estimates |

## Required deliverables

1. Source capture preserved beside the system.
2. Foundations board: color, type, spacing, grid, radius, effects, and icons.
3. Controls and components board with variants and states.
4. Patterns, graphics, responsive behavior, motion, coverage, and usage rules.
5. Origin labels, accessibility checks, source provenance, and limitations.

Values are labeled as **Extracted**, **Estimated**, **Inferred**, **Generated**, **Source-specific**, or **Updated**.

## Example

> Extract a reusable design system from this authorized URL and build the boards in Figma. Use a 1440 × 900 viewport, preserve the source capture, and label all estimated values.

The workflow is tool-agnostic and adapts to Claude Design, Figma, Pencil, Paper, or another editable design environment available to the host agent.

More ready-to-use requests are available in [examples/prompts.md](examples/prompts.md).

## Responsible use

Use only sources you own or are authorized to analyze. Do not republish protected brand assets, personal data, secrets, authenticated content, or hidden application state. Do not bypass access controls.

See [full documentation](docs/design-system-extraction.md) and [the skill definition](SKILL.md).

## Contributing

Issues and focused pull requests are welcome. Read the [contribution guide](docs/CONTRIBUTING.md) before proposing changes. Security concerns should follow the [security policy](docs/SECURITY.md).

## License

[MIT](LICENSE)
