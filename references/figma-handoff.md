# Figma handoff — recipe

Run only after the HTML guide is delivered and the user opted in (Step 3c), or when the original request named Figma.

## 0. Connect

- Preferred: **figma-console** MCP with the **Desktop Bridge** plugin running in the target file (Plugins → Development → Figma Desktop Bridge). Alternative: the official Figma MCP (`use_figma`), following its own skills.
- Check the connection first (`figma_list_open_files` / `figma_diagnose`). Lock the target file (`figma_navigate` with `lock: true`) so commands cannot land in another open file.
- If the bridge is not connected, ask the user to open the file and run the plugin, then continue where you stopped.
- Several figma-console servers (one per Claude session/app) can pair with the same plugin on ports 9223–9232. If layers you built disappear, another session or an Undo is touching the file: tell the user, ask them not to edit during the run, rebuild, and re-read counts.

## 1. Page and layout

- One page named **"Design System"**. Never delete or rename the user's existing pages with content. On the Free plan (3 pages max) reuse an empty page and say so.
- One Figma **Section per level**, stacked top to bottom, left edges aligned, ~400px between Sections, named exactly:
  `00 Source capture` · `01 Tokens` · `02 Atoms` · `03 Molecules` · `04 Organisms` · `05 Sections & templates` · `06 Pages` · `07 Flows` · `08 Product & rules` · `09 Coverage`
- An **Index** frame at the very top listing the 10 Sections (code, name, what is inside).
- Inside each Section: frames in one row, 160px gaps, equal top edges, no overlap, nothing taller than 8000px (split boards and long pages).
- The first frame in each Section is a **note frame**: breadcrumb `[BRAND] / DESIGN SYSTEM / 0X NAME`, title, one-line purpose, what is inside, how to use it for handoff, origin legend.
- Doc boards are 1440 wide, white, 64px padding, vertical auto layout. Boards that show 1:1 organisms or sections may be the source width (for example 1680) — state it.

## 2. Tokens (01)

- One collection per family (Color, Space, Radius, Size, Grid) with one mode (Free plan). Slash names group them: `bg/canvas`, `ink/default`, `accent/default`, `space/16`, `radius/none`, `size/btn-h`, `grid/col`.
- Avoid a variable named like a group (`ink` and `ink/strong`): use `ink/default`.
- Text styles named `display/xl`, `heading/h2`, `body/md`, `mono/label`… with size, line height (px), tracking (%), case.
- A grid style for the column grid.
- Bind every fill, stroke, gap, padding, radius and size to variables (`setBoundVariableForPaint`, `setBoundVariable`). Text uses text styles.

## 3. Components (02–05)

- Every reusable unit is a main component, or a component set when it has variants. Variant property names: `State`, `Tone`, `Type`, `Dir`, `Kind`, `Image`.
- Name with code + path: `A-01 Button/Light` (set) with variants `State=Default|Hover|Focus|Disabled`. Give every main component a **description**: what it is, made of which codes, origin.
- Text properties for labels (`Label`, `Number`, `Heading`), boolean properties for optional parts (`Popular`).
- Molecules contain only atom instances, organisms molecule + atom instances, sections organism instances (plus section headers/quotes). Expose nested instances (`isExposedInstance = true`) only after the instance is inside the component and only when the nested component has properties.
- Sections are 1:1 components at the source width with the grid overlay atom, background texture atoms and organism instances placed on the column grid.
- Textures and overlays (grid lines, halftone, grain, dither photo slots) are atoms with image fills, so sections stay instance-only.

## 4. Pages, flows, coverage (06–09)

- 06: each page = vertical auto-layout frame of section instances, split at section boundaries under 8000px, with a frame of the source screenshots beside each part.
- 07: one row per journey (`J-01 …`), steps are section instances scaled to 25% with captions, joined by arrow vectors (`setVectorNetworkAsync`, end cap `ARROW_LINES`). Add prototype reactions between steps where possible and name flow starting points `J-01`, `J-02`, `J-03`.
- 08: experience, take vs leave, graphic inventory tiles (reusable atoms as instances, Source-specific crops of the capture via `imageTransform`), usage rules, limitations, changelog.
- 09: **Coverage matrix** frame (auto-layout table: Item · Code · Level · Location · Status badge Covered green / Partial orange / Missing red) with a row for every component and every captured section, and a **Totals** frame (variables, text styles, atoms, molecules, organisms, sections, templates).

## 5. Images

- `figma.createImageAsync(url)` only accepts domains in the plugin manifest. For local files, serve them on a port the manifest allows (the Desktop Bridge allows `http://localhost:9223–9232`) and `fetch()` them inside the plugin, then `figma.createImage(bytes)`. Stop the server afterwards.
- Never leave gray boxes where a captured graphic belongs. Source photos and logos appear only as Source-specific reference tiles.

## 6. Scripting tips (figma_execute)

- Store a helper library once in `figma.root.setPluginData('H', src)` and load it in every call with `new Function(src)()`; keep a component registry (code → node id) in plugin data and rebuild it by scanning components if it drifts.
- `appendChild` returns nothing; set positions after appending. Set `layoutSizingHorizontal = 'FILL'` only after the child is in an auto-layout parent.
- Auto-layout chips with long labels must hug (`primaryAxisSizingMode = 'AUTO'`) or text overflows.
- Rotations pivot on the top-left corner: after rotating, read `absoluteBoundingBox` and shift the node into place.
- Vector networks need `setVectorNetworkAsync` (dynamic page access).
- On a failed run, remove partial nodes before retrying.

## 7. Gates before reporting

1. Read back every M/O/S component and list the main component of each nested instance: each must belong to a smaller level (report intended exceptions).
2. No SOLID fill or stroke inside components without a bound variable.
3. Bounding boxes of every Section and top-level frame: no overlaps, equal top edges, gaps ≥ 120px, no label overlaps.
4. Counts: variables, text styles, components per level, sections, templates — compare with the coverage matrix.
5. Screenshot every Section and check for clipped text, empty panels, blank asset tiles.
6. Report in the user's language: counts, what moved or was created, what was not touched, limitations.
