# Live HTML guide — spec

The HTML guide is the default deliverable of this skill. It documents the **source**, not a new build. Values, screenshots and components come from the capture.

## Page skeleton

```text
<nav class="idx">           sticky index: 00 … 09 + DESIGN.md
<main>
  <section id="overview">   00 Overview + source capture + Copy CSS + DESIGN.md buttons
  <section id="tokens">     01 Tokens
  <section id="atoms">      02 Atoms
  <section id="molecules">  03 Molecules
  <section id="organisms">  04 Organisms (screenshots + anatomy table + live rebuilds)
  <section id="sections">   05 Sections & templates (section screenshots, captions with codes)
  <section id="pages">      06 Pages (page rhythm, section order)
  <section id="flows">      07 Flows (journeys as step chips)
  <section id="product">    08 Product & rules (experience, take vs leave, rules, limitations)
  <section id="coverage">   09 Coverage (totals + matrix)
  <section id="design-md">  DESIGN.md (structure outline + Copy + Download)
</main>
<style id="ds">             copyable component CSS only (tokens as custom properties + classes)
```

Every level section starts with: breadcrumb `[BRAND] / DESIGN SYSTEM / 0X LEVEL`, H2 title, one-line purpose, origin legend, and a **copy icon on the heading** that copies the whole level as Markdown.

## Copy on every part

| Part | Copy icon copies | Format |
| --- | --- | --- |
| Level heading (00–09) | that level as Markdown, same text the DESIGN.md generator emits for it | Markdown |
| Color swatch | `--ob-accent: #ED4F00; /* accent/default */` | CSS |
| Type row | the CSS rule of its class from `#ds` | CSS |
| Atom / molecule / organism card | its live HTML snippet | HTML |
| Section screenshot | `S-05 Case studies · inverse · uses M-02, O-08` | Text |
| Any table | the table as Markdown | Markdown |
| Toolbar | Copy CSS (whole `#ds` block), Copy DESIGN.md, Download DESIGN.md | CSS / Markdown / file |

Icon button pattern (square, no radius, matches mono UI):

```html
<button class="ci" data-copy-kind="html" data-ref="A-01" aria-label="Copy HTML of A-01">
  <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" aria-hidden="true">
    <rect x="9" y="9" width="12" height="12"/><path d="M5 15V3h12"/>
  </svg>
</button>
```

```css
.ci{display:inline-grid;place-items:center;width:28px;height:28px;border:1px solid var(--line);background:#fff;color:var(--ink);cursor:pointer}
.ci:hover,.ci:focus-visible{background:var(--accent);border-color:var(--accent);color:#fff;outline:0}
```

Clipboard helper (must run inside the click handler):

```js
function copy(text){
  const done=()=>showToast('Copied');
  const fallback=()=>{const ta=document.createElement('textarea');ta.value=text;document.body.appendChild(ta);ta.select();try{document.execCommand('copy')}catch(e){}ta.remove();done()};
  try{navigator.clipboard.writeText(text).then(done,fallback)}catch(e){fallback()}
}
```

## DESIGN.md export

- Build the Markdown from the same data arrays that render the page (colors, type, atoms, molecules, organisms, anatomy, sections) and from the rendered tables, so the page and the file never disagree.
- Structure: `references/design-md.md`.
- **Copy DESIGN.md**: writes the full text to the clipboard.
- **Download DESIGN.md**: only when the guide is a standalone HTML file: `new Blob([md],{type:'text/markdown'})` → object URL → `<a download="DESIGN.md">` click → revoke URL. Artifact viewers block every download a page starts, so in an Artifact replace Download with **Show full file** (a `<pre>` with the whole Markdown, selectable) and publish `DESIGN.md` beside the page as a real file; also hand the user the file directly.
- If `navigator.clipboard` is refused, fall back to a hidden textarea + `execCommand('copy')`, and if that fails too, reveal the full text in the `<pre>` for manual selection.
- Show a collapsible "DESIGN.md structure" panel with the outline (H1/H2/H3) so the user sees what the file contains before copying.

## Rules

- Rebuild every A/M/O as live HTML/CSS with neutral copy. Customer logos, mascots, photos and copy are replaced by placeholders in copyable HTML; source screenshots stay as reference only.
- Put the source screenshot above each organism group, with an anatomy table (one row per organism, parts in visual order, made-of codes).
- Style the guide in the source's own world (its ground, type pair and accent).
- Mark sizes taken from screenshots as Estimated.
- Before reporting, confirm every captured section's components have an A/M/O card with a copy icon, and report totals per level.
