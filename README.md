# Design System Extraction

Turn an authorized website, app, screenshot, design file, or codebase into a reusable, traceable design system—then build new pages from it.

[![Install with skills.sh](https://img.shields.io/badge/Install%20with-skills.sh-111111?style=flat-square)](https://skills.sh/yosrend/design-system-extraction)

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

### Automatic agent detection

Run this from your project root. The CLI detects supported agents already configured in the project:

```bash
npx skills add yosrend/design-system-extraction
```

### Codex

```bash
npx skills add yosrend/design-system-extraction \
  --skill design-system-extraction \
  --agent codex \
  -y
```

### Claude Code

```bash
npx skills add yosrend/design-system-extraction \
  --skill design-system-extraction \
  --agent claude-code \
  -y
```

### Cursor

```bash
npx skills add yosrend/design-system-extraction \
  --skill design-system-extraction \
  --agent cursor \
  -y
```

### Windsurf

```bash
npx skills add yosrend/design-system-extraction \
  --skill design-system-extraction \
  --agent windsurf \
  -y
```

### GitHub Copilot

```bash
npx skills add yosrend/design-system-extraction \
  --skill design-system-extraction \
  --agent github-copilot \
  -y
```

### Every detected agent

```bash
npx skills add yosrend/design-system-extraction \
  --skill design-system-extraction \
  --agent '*' \
  -y
```

Add `--global` to any command to install at user level instead of inside the current project.

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

Phase A, always:
1. Live HTML guide organized by 8 levels (tokens, atoms, molecules, organisms, sections, page, flows, product and rules) plus a coverage audit, with live rebuilt components and a copy icon on every part (HTML, CSS, Markdown).
2. DESIGN.md generated from the guide, copyable from the page and saved next to it.
3. Reference screenshots per section, origin labels, accessibility findings and limitations.

Then the agent asks whether to send the system to Figma or another design tool. If not, the skill ends at HTML.

Phase B, only on request:
4. One `Design System` page with Sections 00 Source capture to 09 Coverage: variables, text styles, registered components per level, rebuilt sections and pages, flows, rules.
5. Optional new site, variations and responsive expansion built from the system.

Values are labeled as **Extracted**, **Estimated**, **Inferred**, **Generated**, **Source-specific**, or **Updated**.

## Example

> Extract a reusable design system from this authorized URL. Give me the HTML guide and DESIGN.md first, then ask whether to send it to Figma.

The workflow is tool-agnostic and adapts to Claude Design, Figma, Pencil, Paper, or another editable design environment available to the host agent.

More ready-to-use requests are available in [examples/prompts.md](examples/prompts.md).

## Responsible use

Use only sources you own or are authorized to analyze. Do not republish protected brand assets, personal data, secrets, authenticated content, or hidden application state. Do not bypass access controls.

See [full documentation](docs/design-system-extraction.md) and [the skill definition](SKILL.md).

## Contributing

Issues and focused pull requests are welcome. Read the [contribution guide](docs/CONTRIBUTING.md) before proposing changes. Security concerns should follow the [security policy](docs/SECURITY.md).

## License

[MIT](LICENSE)
