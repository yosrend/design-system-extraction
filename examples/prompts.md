# Example Prompts

## Live website (HTML first)

> Extract a reusable design system from this authorized URL at 1680 wide. Build the Live HTML guide (levels 00–09, copy icon on every part, Copy CSS, DESIGN.md export), label every value by origin, then ask me whether to send it to Figma.

## HTML, then Figma handoff

> Same extraction, and when the HTML guide is done send it to my Figma file [URL]: one "Design System" page, one Section per level, Coverage separate, variables and components built from instances.

## Screenshot-only source

> Rebuild this screenshot as editable HTML and extract its design system. Mark visually measured values as Estimated, separate brand-specific assets from reusable structure, and document any areas that cannot be inferred reliably.

## Codebase

> Audit this frontend codebase and render its existing UI as the source capture. Extract tokens, components, states, section patterns, responsive behavior, motion, and accessibility findings. Bind components to variables where supported.

## Build a new page

> Using only the extracted design system, create a 1440 px landing page for [product]. Preserve the source's visual character without copying its layout or brand assets. Use real copy, fix documented contrast failures, and list any generated additions.

## Sync after feedback

> Apply these targeted changes to the existing page: [feedback]. Then update the design-system boards, mark changed items as Updated, and add a concise changelog entry on 08 Product & rules.
