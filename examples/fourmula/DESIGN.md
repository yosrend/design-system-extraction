# Fourmula Design System

> Source: https://fourmula.ai · captured 2026-11-26 at 1440 × 900 · method: headless DOM + computed styles + section screenshots
> Origin labels: Extracted · Estimated · Inferred · Generated · Source-specific · Updated
> Codes A-xx (atoms), M-xx (molecules), O-xx (organisms), S-xx (sections), T-xx (templates), J-xx (flows) are shared by this guide, DESIGN.md and Figma.
> Figma (optional): page "Design System" → Sections 00 Source capture … 09 Coverage.

## 00 White studio, orange signal

Purpose: the reference for building anything in Fourmula's visual language.

Extracted from fourmula.ai (Webflow, GSAP) on 26 Nov 2026 at 1440 × 900 with a headless browser: computed styles, CSS custom properties and 12 section screenshots. The site sizes everything in rem against a root of 13.31px at 1440 wide (1rem ≈ 0.924vw); values below are the 1440 pixel equivalents. Components are rebuilt as live HTML with neutral copy and placeholder media.

### Character

| ASPECT | RULE | ORIGIN |
| --- | --- | --- |
| Grounds | Pure white page; #F7F7F7 rounded panels (radius 40) inset 6.65px from the viewport edge for feature and footer blocks. | EXTRACTED |
| Type | One family (SF Pro Display) in two weights: 400 for display, 500 for small UI. Huge tight display (−3% tracking) against tiny 10–15px labels. | EXTRACTED |
| Color | Near-black ink #020108 with alpha steps (64 / 50 / 30 / 20). Colour arrives only as full-bleed gradients that all resolve to orange #FC7404. | EXTRACTED |
| Grid | Left rail 406px (≈ 28%) + content column, separated by 1px #D7D7D6 rules; sections open with a rail label or a giant headline. | EXTRACTED |
| Shape | Pills for every control, radius 40 for panels, 26.6 for glass cards, rotated squircles (≈30%) for hero photos. No shadows. | EXTRACTED |
| Font note | SF Pro Display is licensed; this guide renders with Inter as the open stand-in. | INFERRED |

## 01 Tokens

Purpose: every value components are allowed to use. Handoff: map these 1:1 to CSS variables or Figma variables.

### 01 / Color

| Token | CSS variable | Value | Use |
| --- | --- | --- | --- |
| ink/default | `--fm-ink` | #020108 | Headlines, text, primary buttons |
| ink/64 | `--fm-ink-64` | rgba(2,1,8,.64) | Second-level text, muted word rows |
| ink/50 | `--fm-ink-50` | rgba(2,1,8,.5) | Muted headline line, captions |
| ink/30 | `--fm-ink-30` | rgba(2,1,8,.3) | Third word row (fails contrast) |
| ink/20 | `--fm-ink-20` | rgba(2,1,8,.2) | Icon button ring |
| surface/white | `--fm-surface` | #FFFFFF | Page ground, light buttons |
| surface/panel | `--fm-panel` | #F7F7F7 | Rounded panels, logo tiles, footer |
| line/default | `--fm-line` | #D7D7D6 | Rail and row rules |
| menu/bg | `--fm-menu` | #272727 | Header menu pill |
| white/20 | `--fm-white-20` | rgba(255,255,255,.2) | Glass cards, progress chip, rules on colour |
| white/50 | `--fm-white-50` | rgba(255,255,255,.5) | Muted text on colour |
| dark/bg | `--fm-dark` | #111111 | Dark theme ground, app mock |
| dark/line | `--fm-line-dark` | #2A2A30 | Rules in dark theme |
| accent/orange | `--fm-orange` | #FA4A00 | Gradient start, status |
| accent/orange-2 | `--fm-orange-2` | #FC7404 | Gradient end, app chips, selected state |
| dot/idle | `--fm-dot` | #D9D9D9 | Footer dot field |

### 02 / Gradients (step slides)

| Token | CSS variable | Value | Use |
| --- | --- | --- | --- |
| gradient/orange | `--fm-g-orange` | linear-gradient(180deg,#FA4A00 0%,#FB5A02 40%,#FC7404 100%) | Step 01 · #FA4A00 → #FC7404 |
| gradient/sky | `--fm-g-sky` | linear-gradient(180deg,#48A3D0 0%,#85968C 35%,#C9965D 65%,#FC7404 100%) | Step 02 · #48A3D0 → #FC7404 |
| gradient/violet | `--fm-g-violet` | linear-gradient(180deg,#3B56FF 0%,#8D6AAC 35%,#A86F80 60%,#FD7509 100%) | Step 03 · #3B56FF → #FD7509 |
| gradient/crimson | `--fm-g-crimson` | linear-gradient(180deg,#9C0202 0%,#BC2A03 40%,#CB3F02 65%,#FC7404 100%) | Step 04 · #9C0202 → #FC7404 |

Contrast (Inferred): ink/30 on white ≈ 2.0:1 and 10–12px white text on #FB5A02 ≈ 3.1:1 both fail WCAG AA for small text. New work: use ink/64 minimum for text, and 16px+ medium on gradients.

### 03 / Typography

| TOKEN | SPECIMEN | SPEC (1440) | USE |  |
| --- | --- | --- | --- | --- |
| display/h2 | Made by AI. | 400 · 99.8/99.8 · −3% · 7.5rem | Section statements (What, FAQ) |
| display/h1 | Re-shot. | 400 · 73.2/68.8 · −3% · 5.5rem | Hero, steps intro |
| display/h2-5 | Add products | 400 · 53.2/53.2 · −3% · 4rem | Step slide titles |
| heading/h3 | Studio-quality | 500 · 43.3/45.4 · −3% · 3.25rem | Panel captions |
| title/3 | (PB) | 500 · 20/30 · −1% · 1.5rem | Paren tags |
| body/1 | Upload one product and get every angle. | 400 · 15/21.8 · 1.125rem | Lead text |
| tag | What you can do | 400 · 15/22.5 · 1.125rem | Rail labels |
| button | Get started | 400 · 14.1/17 · −2% · 1.0625rem | Buttons, menu |
| title/2 | AI Fashion Photoshoot | 500 · 11.6 · −1% · 0.875rem | UI labels (most used) |
| small/1 | ©2026 · Scroll down | 400 · 10/15 · −1% · 0.75rem | Captions, legal |

### 04 / Spacing, radius, layout

| TOKEN | VALUE | USE | ORIGIN |
| --- | --- | --- | --- |
| space/1 … 7 | 6.65 · 9.98 · 13.3 · 19.96 · 26.6 · 46.6 · 66.5 (0.5 · 0.75 · 1 · 1.5 · 2 · 3.5 · 5 rem) | Panel inset 6.65 · row padding 26.6 · panel padding 66.5 | EXTRACTED |
| radius/sm | 6.65px | App screen mock, logo tiles | EXTRACTED |
| radius/md | 12px | Media cards, drop tile | ESTIMATED |
| radius/card | 26.6px | Glass demo cards, icon buttons | EXTRACTED |
| radius/panel | 40px (3rem) | Feature panels, footer card | EXTRACTED |
| radius/pill | 999px | Buttons, menu pill, progress, chips | EXTRACTED |
| layout/rail | 406px left rail + content; rules 1px #D7D7D6 | What, How, FAQ sections | EXTRACTED |
| layout/section | 100vh steps (900 at 1440); panels 932 tall | Hero, step slides, AI panels | EXTRACTED |
| size/control | Button 40 · menu pill 32 · icon button 27 · progress 24 | Header + CTAs | EXTRACTED |

### 05 / Effects & motion

| TOKEN | VALUE | ORIGIN |
| --- | --- | --- |
| shadow | None anywhere. Depth = panel fills and white @20% glass. | EXTRACTED |
| motion/button | Label duplicated; on hover the stack slides up one line (text roll), ~450ms ease-in-out. | ESTIMATED |
| motion/steps | Four 100vh slides pinned on scroll; the gradient changes per step, big number counts 01–04. | EXTRACTED |
| motion/progress | Header pill shows page scroll 0–100%. | EXTRACTED |
| motion/orbit | Hero photos rotate slowly around the upload tile. | ESTIMATED |
| motion/dots | Footer dot field reacts to the pointer (dots turn ink). | ESTIMATED |
| motion/reduced | No pinning, no orbit, no text roll; slides stack as normal sections. | GENERATED |

## 02 Atoms

Purpose: single elements. Hover the buttons to see the text roll. Every card copies its HTML.

### A-01 Button / Primary
- Made of: pill 40 · ink · button type · text-roll hover

```html
<button class="fm-btn ">
<span>Get started</span>
<span aria-hidden="true">Get started</span>
</button>
```

### A-02 Button / Light
- Made of: pill 40 · white · ink text · on colour

```html
<button class="fm-btn fm-btn--light">
<span>Get started</span>
<span aria-hidden="true">Get started</span>
</button>
```

### A-03 Button / Disabled
- Made of: Generated state

```html
<button class="fm-btn" disabled>
<span>Unavailable</span>
</button>
```

### A-04 Icon button / Account
- Made of: 27 circle · ring ink/20

```html
<button class="fm-icon-btn" aria-label="Account">
<svg viewBox="0 0 24 24" fill="currentColor">
<circle cx="12" cy="8" r="4"/>
<path d="M4 21c0-4.4 3.6-7 8-7s8 2.6 8 7z"/>
</svg>
</button>
```

### A-05 Menu toggle
- Made of: burger 18 × 2 lines + label

```html
<span class="fm-pill" style="padding-right:12px">
<span class="fm-burger" aria-hidden="true">
<i>
</i>
<i>
</i>
</span>Menu</span>
```

### A-06 Theme toggle
- Made of: 24 circle · ring white/20 · moon icon

```html
<span class="fm-pill" style="padding:0 4px">
<span class="fm-theme">
<svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="#fff" stroke-width="2">
<path d="M21 12.8A9 9 0 1 1 11.2 3a7 7 0 0 0 9.8 9.8z"/>
</svg>
</span>
</span>
```

### A-07 Progress chip
- Made of: pill 24 · white/20 · scroll %

```html
<span class="fm-pill" style="padding:0 4px">
<span class="fm-progress">42%</span>
</span>
```

### A-08 Tag / Rail label
- Made of: tag 15 · ink

```html
<span class="fm-tag">What you can do</span>
```

### A-09 Section label
- Made of: title/2 11.6 medium · dot

```html
<span class="fm-label">AI Fashion Photoshoot</span>
```

### A-10 Bullet tag
- Made of: small 10 medium · square dot

```html
<span class="fm-bullet" style="color:#fff">14+ model presets</span>
```

### A-11 Paren tag + step number
- Made of: title/3 at 40% · display 99.8

```html
<div style="display:flex;gap:28px;align-items:center;color:#fff">
<span class="fm-paren">(AB)</span>
<span class="fm-num" style="font-size:72px">01</span>
</div>
```

### A-12 Drop tile
- Made of: 88 · radius 12 · line ring · paperclip

```html
<div style="display:grid;justify-items:center">
<div class="fm-drop">
<svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6">
<path d="M21 12.5 12.6 20.9a5 5 0 0 1-7.1-7.1l8.5-8.5a3.3 3.3 0 0 1 4.7 4.7l-8.5 8.5a1.7 1.7 0 0 1-2.4-2.4l7.8-7.8"/>
</svg>
</div>
<div class="fm-drop-cap">Upload or drop your assets</div>
</div>
```

### A-13 Photo tile (squircle)
- Made of: rotated −28° · radius 30% · placeholder media

```html
<div class="fm-tile">
<i>
</i>
</div>
```

### A-14 FAQ toggle
- Made of: 12px plus · ink 1px

```html
<span class="fm-plus">
</span>
```

### A-15 Expand icon
- Made of: 16 · four arrows · ink

```html
<span style="color:#020108">
<svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8">
<path d="M12 3v6m0 6v6M3 12h6m6 0h6M9 6l3-3 3 3M9 18l3 3 3-3M6 9l-3 3 3 3M18 9l3 3-3 3"/>
</svg>
</span>
```

### A-16 Logo tile
- Made of: 106 × 84 · panel · radius 6.65 · grey logo

```html
<div class="fm-logo-tile">logoipsum</div>
```

### A-17 Spinner
- Made of: 18 · conic ring

```html
<span class="fm-spin" role="img" aria-label="Loading">
</span>
```

### A-18 Round action
- Made of: 22 circle · orange download / muted trash

```html
<span style="display:flex;gap:6px">
<button class="fm-round fm-round--muted" aria-label="Delete">
<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2">
<path d="M4 7h16M9 7V4h6v3M6 7l1 13h10l1-13"/>
</svg>
</button>
<button class="fm-round" aria-label="Download">
<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4">
<path d="M12 4v12m-5-5 5 5 5-5M5 20h14"/>
</svg>
</button>
</span>
```

### A-19 Radio
- Made of: 12 circle · selected orange-2

```html
<span style="display:flex;gap:12px">
<span class="fm-radio" role="radio" aria-checked="false">
</span>
<span class="fm-radio" role="radio" aria-checked="true">
</span>
</span>
```

### A-20 Status chip
- Made of: pill 22 · orange-2 outline / fill

```html
<span style="display:flex;gap:6px">
<span class="fm-chip">15 ◎</span>
<span class="fm-chip fm-chip--fill">+ Assets</span>
</span>
```

### A-21 Dot
- Made of: 10 circle · idle #D9D9D9 · active ink

```html
<span style="display:flex;gap:8px">
<span class="fm-dot">
</span>
<span class="fm-dot on">
</span>
<span class="fm-dot">
</span>
</span>
```

### A-22 Brand mark (placeholder)
- Made of: Generated stand-in for the source logo

```html
<span class="fm-mark">
<i>
</i>Brand</span>
```

### A-23 Rule
- Made of: 1px line/default (light) · white/20 on colour

```html
<div style="width:100%;display:grid;gap:14px">
<hr style="border:0;border-top:1px solid #D7D7D6;margin:0">
<div style="background:#FB5A02;padding:10px">
<hr style="border:0;border-top:1px solid rgba(255,255,255,.2);margin:0">
</div>
</div>
```

## 03 Molecules

Purpose: small groups of atoms. The "=" line lists the atom codes each one is built from.

### M-01 Header menu pill
- Made of: A-05 + A-06 + A-07

```html
<span class="fm-pill">
<span class="fm-burger" aria-hidden="true">
<i>
</i>
<i>
</i>
</span>Menu<span class="fm-theme">
<svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="#fff" stroke-width="2">
<path d="M21 12.8A9 9 0 1 1 11.2 3a7 7 0 0 0 9.8 9.8z"/>
</svg>
</span>
<span class="fm-progress">0%</span>
</span>
```

### M-02 Header actions
- Made of: A-04 + A-01

```html
<span class="fm-actions">
<button class="fm-icon-btn" aria-label="Account">
<svg viewBox="0 0 24 24" fill="currentColor">
<circle cx="12" cy="8" r="4"/>
<path d="M4 21c0-4.4 3.6-7 8-7s8 2.6 8 7z"/>
</svg>
</button>
<button class="fm-btn ">
<span>Get started</span>
<span aria-hidden="true">Get started</span>
</button>
</span>
```

### M-03 Rail heading
- Made of: A-08 + display/h2

```html
<div class="fm-headblock">
<span class="fm-tag">What you can do</span>
<h2 class="fm-h2" style="font-size:52px">On-brand visuals.<br>Made by AI.</h2>
</div>
```

### M-04 Feature caption
- Made of: heading/h3 + body/1

```html
<div class="fm-caption">
<h3 class="fm-h3">Studio-quality,<br>without the studio.</h3>
<span class="fm-micro" style="color:#020108">Upload one product and get every angle and look you need.</span>
</div>
```

### M-05 Bullet pair
- Made of: A-10 ×2 + A-23

```html
<div class="fm-bullets">
<div>
<span class="fm-bullet">14+ model presets</span>
</div>
<div>
<span class="fm-bullet">Multiple pose options</span>
</div>
</div>
```

### M-06 Step lead
- Made of: body (first line white, rest white/50) + A-02

```html
<div class="fm-lead">
<p>Store your products,<br>
<span>shots and brand look<br>in one place.</span>
</p>
<button class="fm-btn fm-btn--light fm-btn--sm">
<span>Get started</span>
<span aria-hidden="true">Get started</span>
</button>
</div>
```

### M-07 Word row
- Made of: display 58 + A-23 · states ink / 64 / 30

```html
<div>
<div class="fm-word">Create images</div>
<div class="fm-word fm-word--64">Make videos</div>
<div class="fm-word fm-word--30">Stay on-brand</div>
</div>
```

### M-08 FAQ row
- Made of: question + A-14 + A-23 · open state Generated

```html
<details class="fm-faq">
<summary>What can it create for my brand?<span class="fm-plus">
</span>
</summary>
<p>Product shots, model photos and short videos in your brand look.</p>
</details>
```

### M-09 Face option card
- Made of: A-13 media + A-19 · selected = orange ring

```html
<div style="display:flex;gap:8px">
<div class="fm-face">
<span class="fm-radio" role="radio" aria-checked="false">
</span>
<i>
</i>
</div>
<div class="fm-face sel">
<span class="fm-radio" role="radio" aria-checked="true">
</span>
<i>
</i>
</div>
</div>
```

### M-10 Result card
- Made of: media + A-18 ×2 + caption

```html
<div class="fm-result">
<div class="acts">
<button class="fm-round fm-round--muted" aria-label="Delete">
<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2">
<path d="M4 7h16M9 7V4h6v3M6 7l1 13h10l1-13"/>
</svg>
</button>
<button class="fm-round" aria-label="Download">
<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.4">
<path d="M12 4v12m-5-5 5 5 5-5M5 20h14"/>
</svg>
</button>
</div>
<span class="cap">Sand</span>
</div>
```

### M-11 Processing card
- Made of: A-17 + label · loading state

```html
<div class="fm-processing">
<span class="fm-spin" style="color:#fff">
</span>
</div>
```

### M-12 App toolbar pill
- Made of: A-17 + A-20 ×2 + A-18 + avatar

```html
<span class="fm-toolbar">
<span class="fm-spin">
</span>
<span class="fm-chip">15 ◎</span>
<span class="fm-chip fm-chip--fill">+ Assets</span>
<span class="fm-avatar">
</span>
</span>
```

### M-13 Footer link column
- Made of: small/1 links ×n

```html
<div class="fm-links">
<a href="#">Product shots</a>
<a href="#">Videos</a>
<a href="#">Privacy policy</a>
<a href="#">Terms of service</a>
</div>
```

### M-14 Consent card
- Made of: body + A-01 · Generated layout

```html
<div class="fm-consent">
<span class="fm-micro" style="color:#020108">We use cookies to improve the site.</span>
<button class="fm-btn ">
<span>Accept all</span>
<span aria-hidden="true">Accept all</span>
</button>
</div>
```

## 04 Organisms

Purpose: large reusable blocks. Anatomy lists parts in visual order; live rebuilds use placeholder media.

- O-03 Product showcase panel
- O-07 Step slide (orange)

### Anatomy

| CODE | ORGANISM | ANATOMY, IN VISUAL ORDER | MADE OF |
| --- | --- | --- | --- |
| O-01 | Header | Logo mark left · dark menu pill centred (burger + Menu, theme toggle, scroll %) · account ring + black Get started right; floats over every section | A-22, M-01, M-02 |
| O-02 | Hero orbit | Eight rotated squircle photos on a circle · white drop tile with paperclip and caption in the centre · style chips fading on the right | A-12, A-13 ×8 |
| O-03 | Product showcase panel | #F7F7F7 panel r40 · label top-left · black product tile → dark app screen with 2×5 shot grid and orange toolbar chips · caption bottom-left · expand icon bottom-right | T-02, A-09, M-04, A-15, A-20 |
| O-04 | Dual feature panels | Two r40 panels side by side · photo collages (rounded 12) · caption each | T-02 ×2, M-04 ×2 |
| O-05 | Word list + CTA | Rail with 'AI that' + Get started · three giant words with rules, fading ink → 64 → 30 | T-01, M-07 ×3, A-01 |
| O-06 | Logo marquee | 'Trusted by' label · grey logo tiles r6.65 sliding with edge fade | A-09, A-16 ×n |
| O-07 | Step slide | Full-bleed gradient · title + (tag) + giant number · 2-col bullet rules · lead + light pill · glass card with the step's demo UI | T-03, A-11, M-05, M-06, M-09/M-10/M-11/M-12 |
| O-08 | FAQ list | Giant two-line statement · six rows with plus toggles and rules | M-08 ×6 |
| O-09 | Footer card | r40 panel · logo + wordmark · two link columns · legal + copyright · interactive dot matrix | A-22, M-13 ×2, A-21 grid |

### Live rebuilds

### O-01 Header
- Made of: A-22 + M-01 + M-02

```html
<div class="fm-header">
<span class="fm-mark">
<i>
</i>
</span>
<span class="fm-pill">
<span class="fm-burger">
<i>
</i>
<i>
</i>
</span>Menu<span class="fm-theme">
<svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="#fff" stroke-width="2">
<path d="M21 12.8A9 9 0 1 1 11.2 3a7 7 0 0 0 9.8 9.8z"/>
</svg>
</span>
<span class="fm-progress">0%</span>
</span>
<span class="fm-actions">
<button class="fm-icon-btn" aria-label="Account">
<svg viewBox="0 0 24 24" fill="currentColor">
<circle cx="12" cy="8" r="4"/>
<path d="M4 21c0-4.4 3.6-7 8-7s8 2.6 8 7z"/>
</svg>
</button>
<button class="fm-btn ">
<span>Get started</span>
<span aria-hidden="true">Get started</span>
</button>
</span>
</div>
```

### O-02 Hero orbit
- Made of: A-12 + A-13 ×8 on a circle

```html
<div class="fm-orbit">
<div class="fm-tile" style="left:138px;top:8px;transform:rotate(-28deg)">
<i>
</i>
</div>
<div class="fm-tile" style="left:226.38834764831844px;top:40.218254069479784px;transform:rotate(-19deg)">
<i>
</i>
</div>
<div class="fm-tile" style="left:263px;top:118px;transform:rotate(-10deg)">
<i>
</i>
</div>
<div class="fm-tile" style="left:226.38834764831844px;top:195.78174593052023px;transform:rotate(-1deg)">
<i>
</i>
</div>
<div class="fm-tile" style="left:138px;top:228px;transform:rotate(8deg)">
<i>
</i>
</div>
<div class="fm-tile" style="left:49.61165235168157px;top:195.78174593052023px;transform:rotate(17deg)">
<i>
</i>
</div>
<div class="fm-tile" style="left:13px;top:118.00000000000001px;transform:rotate(26deg)">
<i>
</i>
</div>
<div class="fm-tile" style="left:49.61165235168154px;top:40.218254069479784px;transform:rotate(35deg)">
<i>
</i>
</div>
<div style="position:absolute;left:126px;top:98px;display:grid;justify-items:center">
<div class="fm-drop">
<svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6">
<path d="M21 12.5 12.6 20.9a5 5 0 0 1-7.1-7.1l8.5-8.5a3.3 3.3 0 0 1 4.7 4.7l-8.5 8.5a1.7 1.7 0 0 1-2.4-2.4l7.8-7.8"/>
</svg>
</div>
<div class="fm-drop-cap">Upload or drop</div>
</div>
</div>
```

### O-03 Product showcase panel
- Made of: T-02 panel + A-09 + product tile + app mock + M-04 + A-15

```html
<div class="fm-panel" style="display:grid;gap:22px">
<span class="fm-label">AI Fashion Photoshoot</span>
<div style="display:grid;grid-template-columns:110px 1fr;gap:20px;align-items:center">
<div style="height:130px;border-radius:12px;background:#111">
</div>
<div style="height:150px;border-radius:6.65px 0 0 6.65px;background:#111;display:grid;grid-template-columns:repeat(4,1fr);gap:4px;padding:22px 4px 4px">
<i style="background:#E9E7E3;border-radius:4px">
</i>
<i style="background:#E9E7E3;border-radius:4px">
</i>
<i style="background:#E9E7E3;border-radius:4px">
</i>
<i style="background:#E9E7E3;border-radius:4px">
</i>
<i style="background:#E9E7E3;border-radius:4px">
</i>
<i style="background:#E9E7E3;border-radius:4px">
</i>
<i style="background:#E9E7E3;border-radius:4px">
</i>
<i style="background:#E9E7E3;border-radius:4px">
</i>
</div>
</div>
<div style="display:flex;justify-content:space-between;align-items:end">
<div class="fm-caption">
<h3 class="fm-h3">Studio-quality,<br>without the studio.</h3>
</div>
<svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8">
<path d="M12 3v6m0 6v6M3 12h6m6 0h6M9 6l3-3 3 3M9 18l3 3 3-3M6 9l-3 3 3 3M18 9l3 3-3 3"/>
</svg>
</div>
</div>
```

### O-04 Dual feature panels
- Made of: T-02 ×2 + media collage + M-04 + A-15

```html
<div style="display:grid;grid-template-columns:1fr 1fr;gap:6px">
<div class="fm-panel" style="padding:18px;display:grid;gap:14px">
<span class="fm-label">AI Product Shots</span>
<div style="display:grid;grid-template-columns:1fr 1fr;gap:6px">
<i style="height:70px;border-radius:10px;background:#C8BCA7">
</i>
<i style="height:70px;border-radius:10px;background:#D9A15E">
</i>
</div>
<h3 class="fm-h3" style="font-size:20px">Your product,<br>new scenes.</h3>
</div>
<div class="fm-panel" style="padding:18px;display:grid;gap:14px">
<span class="fm-label">AI Video Production</span>
<i style="height:70px;border-radius:10px;background:#6E4A32">
</i>
<h3 class="fm-h3" style="font-size:20px">Campaign video<br>in minutes.</h3>
</div>
</div>
```

### O-05 Word list + CTA
- Made of: T-01 rail + M-07 ×3 + A-01

```html
<div style="display:grid;grid-template-columns:120px 1fr;border-top:1px solid #D7D7D6">
<div style="border-right:1px solid #D7D7D6;padding:16px 12px;display:grid;align-content:space-between">
<span class="fm-h3" style="font-size:24px">AI that</span>
<button class="fm-btn fm-btn--sm">
<span>Get started</span>
<span aria-hidden="true">Get started</span>
</button>
</div>
<div>
<div class="fm-word" style="font-size:34px">Create images</div>
<div class="fm-word fm-word--64" style="font-size:34px">Make videos</div>
<div class="fm-word fm-word--30" style="font-size:34px">Stay on-brand</div>
</div>
</div>
```

### O-06 Logo marquee
- Made of: A-09 label + A-16 ×n, edge fade

```html
<div style="display:grid;grid-template-columns:90px 1fr;gap:12px;align-items:center">
<span class="fm-micro" style="color:#020108">Trusted by</span>
<div class="fm-marquee">
<div class="fm-logo-tile">logoipsum</div>
<div class="fm-logo-tile">logoipsum</div>
<div class="fm-logo-tile">logoipsum</div>
<div class="fm-logo-tile">logoipsum</div>
<div class="fm-logo-tile">logoipsum</div>
</div>
</div>
```

### O-07 Step slide
- Made of: T-03 + A-11 + M-05 + M-06 + glass card (M-09 / M-10 / M-11 / M-12)

```html
<div class="fm-slide">
<div class="top">
<h3 class="fm-h25">Add products<br>and brand.</h3>
<span class="fm-num">01</span>
</div>
<div class="fm-bullets">
<div>
<span class="fm-bullet">14+ model presets</span>
</div>
<div>
<span class="fm-bullet">Multiple pose options</span>
</div>
</div>
<div class="fm-lead">
<p>Store your products,<br>
<span>shots and brand look in one place.</span>
</p>
<button class="fm-btn fm-btn--light fm-btn--sm">
<span>Get started</span>
<span aria-hidden="true">Get started</span>
</button>
</div>
<div class="fm-glass">
<h4>Adjust look</h4>
<div style="display:flex;gap:8px">
<div class="fm-face">
<span class="fm-radio" role="radio" aria-checked="false">
</span>
<i>
</i>
</div>
<div class="fm-face sel">
<span class="fm-radio" role="radio" aria-checked="true">
</span>
<i>
</i>
</div>
<div class="fm-face">
<span class="fm-radio" role="radio" aria-checked="false">
</span>
<i>
</i>
</div>
</div>
</div>
</div>
```

### O-08 FAQ list
- Made of: T-01 + display/h2 + M-08 ×6

```html
<div>
<h2 class="fm-h2" style="font-size:40px;padding:0 20px 12px">Real answers.</h2>
<details class="fm-faq">
<summary>What do I need to start?<span class="fm-plus">
</span>
</summary>
<p>One product photo and your brand look.</p>
</details>
<details class="fm-faq">
<summary>Do I own the assets?<span class="fm-plus">
</span>
</summary>
<p>Yes, everything you export is yours.</p>
</details>
<details class="fm-faq">
<summary>How fast are results?<span class="fm-plus">
</span>
</summary>
<p>Usually within minutes.</p>
</details>
</div>
```

### O-09 Footer card
- Made of: T-02 + A-22 wordmark + M-13 ×2 + legal + dot field (A-21 grid)

```html
<div class="fm-footer">
<div style="display:flex;justify-content:space-between;gap:16px;flex-wrap:wrap">
<span class="fm-mark" style="font-size:30px">
<i style="width:26px;height:26px">
</i>Brand</span>
<div style="display:flex;gap:40px">
<div class="fm-links">
<a href="#">Product shots</a>
<a href="#">Videos</a>
</div>
<div class="fm-links">
<a href="#">Features</a>
<a href="#">Instagram</a>
</div>
</div>
</div>
<span class="fm-micro">© 2026 Company Ltd. All rights reserved.</span>
<div class="fm-dots">
<span class="fm-dot">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot on">
</span>
<span class="fm-dot on">
</span>
<span class="fm-dot on">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot on">
</span>
<span class="fm-dot on">
</span>
<span class="fm-dot on">
</span>
<span class="fm-dot on">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot on">
</span>
<span class="fm-dot on">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot">
</span>
<span class="fm-dot">
</span>
</div>
</div>
```

## 05 Sections & templates

Purpose: one rebuilt section per captured section. Each screenshot copies its structure line.

- S-01 Hero · white · 900px · uses O-01, O-02, display/h1
- S-02 What · white · rail · 347px · uses T-01, M-03
- S-03 Fashion photoshoot · panel · 932px · uses O-03
- S-04 Products & video · panel · 932px · uses O-04
- S-05 How it works · white · rail · 1016px · uses O-05, O-06
- S-06 Steps intro · white · 245px · uses display/h1, body
- S-07 Step 01 · gradient/orange · 900px · uses O-07 (M-09)
- S-08 Step 02 · gradient/sky · 900px · uses O-07 (M-11)
- S-09 Step 03 · gradient/violet · 900px · uses O-07 (M-10)
- S-10 Step 04 · gradient/crimson · 900px · uses O-07 (M-12)
- S-11 FAQ · white · rail · 704px · uses O-08
- S-12 Footer · panel · 812px · uses O-09

### Templates

| CODE | TEMPLATE | STRUCTURE | USED BY |
| --- | --- | --- | --- |
| T-01 | Rail + content | 406px left rail (label or rail headline, bottom CTA) · 1px rule · content column with stacked rows | S-02, S-05, S-11 |
| T-02 | Rounded panel | #F7F7F7 panel, radius 40, 6.65px inset from the viewport, padding 66.5, caption block bottom-left, expand icon bottom-right | S-03, S-04, S-12 |
| T-03 | Gradient step slide | 100vh, full-bleed gradient, title top-left, big number top-right, 2-col bullet rules, lead + light CTA, glass demo card bottom | S-07 – S-10 |

## 06 Home page

Purpose: the order and rhythm of sections on the one captured page.

One page, 9,893px at 1440 wide. Rhythm: white → panels → white rail → four colour slides → white rail → panel footer.

- Hero → What → Fashion photoshoot → Products & video → How it works → Steps intro → Step 01 → Step 02 → Step 03 → Step 04 → FAQ → Footer

## 07 Visitor journeys

Purpose: the paths a visitor takes, from section to the action that moves them on.

### J-01 Try it now

- S-01 Hero → A-12 Drop tile → Upload asset → A-01 Get started

### J-02 Understand → start

- S-02 What → S-03 Photoshoot → S-04 Products & video → S-05 How → S-07–10 Steps → A-02 Get started

### J-03 Doubt → answer

- S-11 FAQ → M-08 Open answer → S-12 Footer links → A-01 Get started (header)

Persistent on every screen: O-01 header (menu pill with scroll %, account, Get started).

## 08 Experience & rules

Purpose: how the whole site should feel, and the rules that keep new work on-brand.

A quiet white studio that turns loud only when it shows the process: product photography carries the warmth, the interface stays black-and-white, and the four gradient slides are the single burst of colour.

### Usage rules

| AREA | RULE |
| --- | --- |
| Headlines | One display line per section, 400 weight, −3% tracking, two short lines max; the second line may drop to ink/50. |
| Text levels | Display 53–100px, then jump straight to 10–20px UI text. No mid-size body paragraphs wider than ~300px. |
| Buttons | Always pills, 40px tall, black on white and white on colour. Hover = text roll, never a colour swap. |
| Colour | Interface is monochrome. Colour only as full-bleed step gradients ending in orange, and as small orange status chips in product UI. |
| Depth | No shadows. Separate with #F7F7F7 panels (radius 40), 1px #D7D7D6 rules and white @20% glass on colour. |
| Imagery | Studio product and model photography on light seamless backgrounds, cropped in rotated squircles or rounded cards (12px). |
| Don't | Coloured buttons on white, drop shadows, sharp corners on controls, long paragraphs, more than one gradient per screen. |

### Take vs leave

| TAKE (STRUCTURE) | LEAVE (SOURCE-SPECIFIC) |
| --- | --- |
| Rail grid, pill controls, text-roll hover, radius-40 panels, gradient step slides, glass demo cards, dot field pattern, scroll-progress pill | Fourmula logo and wordmark, client logos (attentive, yotpo, gorgias…), all model and product photography, 4MLA product names, copy, Awwwards "Site of the Day" badge |

### Limitations

| ITEM | NOTE |
| --- | --- |
| Font | SF Pro Display is licensed; Inter used as stand-in in this guide. |
| Breakpoints | Only 1440 captured. Tablet and mobile not captured. |
| Menu overlay | Menu panel, dark theme toggle and cookie preferences not opened. |
| Motion | Timings and easing estimated from behaviour, not read from GSAP timelines. |
| Gradients | Stops sampled from screenshots (Estimated); the site renders them in canvas/WebGL. |

### Changelog

2026-11-26 · v1 · Initial extraction at 1440 × 900 with skill design-system-extraction v2.0.0.

## 09 Coverage

Purpose: proof that every captured section and component has a home in the system.

- COLOR TOKENS: 20
- TYPE STYLES: 10
- ATOMS: 23
- MOLECULES: 14
- ORGANISMS: 9
- SECTIONS: 12
- TEMPLATES: 3
- FLOWS: 3

### Matrix

| ITEM | CODE | LEVEL | LOCATION | STATUS |
| --- | --- | --- | --- | --- |
| Hero | S-01 | 05 Section | 05 Sections · 01-hero | Covered |
| What | S-02 | 05 Section | 05 Sections · 02-what | Covered |
| Fashion photoshoot | S-03 | 05 Section | 05 Sections · 03-ai-top | Covered |
| Products & video | S-04 | 05 Section | 05 Sections · 04-ai-bottom | Covered |
| How it works | S-05 | 05 Section | 05 Sections · 05-how | Covered |
| Steps intro | S-06 | 05 Section | 05 Sections · 06-list-title | Covered |
| Step 01 | S-07 | 05 Section | 05 Sections · 07-list-slide-1 | Covered |
| Step 02 | S-08 | 05 Section | 05 Sections · 08-list-slide-2 | Covered |
| Step 03 | S-09 | 05 Section | 05 Sections · 09-list-slide-3 | Covered |
| Step 04 | S-10 | 05 Section | 05 Sections · 10-list-slide-4 | Covered |
| FAQ | S-11 | 05 Section | 05 Sections · 11-faq | Covered |
| Footer | S-12 | 05 Section | 05 Sections · 12-footer | Covered |
| Button / Primary | A-01 | 02 Atom | 02 Atoms card | Covered |
| Button / Light | A-02 | 02 Atom | 02 Atoms card | Covered |
| Button / Disabled | A-03 | 02 Atom | 02 Atoms card | Partial |
| Icon button / Account | A-04 | 02 Atom | 02 Atoms card | Covered |
| Menu toggle | A-05 | 02 Atom | 02 Atoms card | Covered |
| Theme toggle | A-06 | 02 Atom | 02 Atoms card | Covered |
| Progress chip | A-07 | 02 Atom | 02 Atoms card | Covered |
| Tag / Rail label | A-08 | 02 Atom | 02 Atoms card | Covered |
| Section label | A-09 | 02 Atom | 02 Atoms card | Covered |
| Bullet tag | A-10 | 02 Atom | 02 Atoms card | Covered |
| Paren tag + step number | A-11 | 02 Atom | 02 Atoms card | Covered |
| Drop tile | A-12 | 02 Atom | 02 Atoms card | Covered |
| Photo tile (squircle) | A-13 | 02 Atom | 02 Atoms card | Partial |
| FAQ toggle | A-14 | 02 Atom | 02 Atoms card | Covered |
| Expand icon | A-15 | 02 Atom | 02 Atoms card | Covered |
| Logo tile | A-16 | 02 Atom | 02 Atoms card | Covered |
| Spinner | A-17 | 02 Atom | 02 Atoms card | Covered |
| Round action | A-18 | 02 Atom | 02 Atoms card | Covered |
| Radio | A-19 | 02 Atom | 02 Atoms card | Covered |
| Status chip | A-20 | 02 Atom | 02 Atoms card | Covered |
| Dot | A-21 | 02 Atom | 02 Atoms card | Covered |
| Brand mark (placeholder) | A-22 | 02 Atom | 02 Atoms card | Partial |
| Rule | A-23 | 02 Atom | 02 Atoms card | Covered |
| Header menu pill | M-01 | 03 Molecule | 03 Molecules card | Covered |
| Header actions | M-02 | 03 Molecule | 03 Molecules card | Covered |
| Rail heading | M-03 | 03 Molecule | 03 Molecules card | Covered |
| Feature caption | M-04 | 03 Molecule | 03 Molecules card | Covered |
| Bullet pair | M-05 | 03 Molecule | 03 Molecules card | Covered |
| Step lead | M-06 | 03 Molecule | 03 Molecules card | Covered |
| Word row | M-07 | 03 Molecule | 03 Molecules card | Covered |
| FAQ row | M-08 | 03 Molecule | 03 Molecules card | Partial |
| Face option card | M-09 | 03 Molecule | 03 Molecules card | Covered |
| Result card | M-10 | 03 Molecule | 03 Molecules card | Covered |
| Processing card | M-11 | 03 Molecule | 03 Molecules card | Covered |
| App toolbar pill | M-12 | 03 Molecule | 03 Molecules card | Covered |
| Footer link column | M-13 | 03 Molecule | 03 Molecules card | Covered |
| Consent card | M-14 | 03 Molecule | 03 Molecules card | Partial |
| Header | O-01 | 04 Organism | 04 Organisms card | Covered |
| Hero orbit | O-02 | 04 Organism | 04 Organisms card | Covered |
| Product showcase panel | O-03 | 04 Organism | 04 Organisms card | Covered |
| Dual feature panels | O-04 | 04 Organism | 04 Organisms card | Covered |
| Word list + CTA | O-05 | 04 Organism | 04 Organisms card | Covered |
| Logo marquee | O-06 | 04 Organism | 04 Organisms card | Covered |
| Step slide | O-07 | 04 Organism | 04 Organisms card | Covered |
| FAQ list | O-08 | 04 Organism | 04 Organisms card | Covered |
| Footer card | O-09 | 04 Organism | 04 Organisms card | Covered |
| Rail + content | T-01 | 05 Template | 05 Templates table | Covered |
| Rounded panel | T-02 | 05 Template | 05 Templates table | Covered |
| Gradient step slide | T-03 | 05 Template | 05 Templates table | Covered |
| Menu overlay | — | 04 Organism | not captured | Missing |
| Dark theme | — | 01 Tokens | dark/bg + dark/line only | Partial |
| Cookie banner | M-14 | 03 Molecule | layout Generated | Partial |
| Tablet / mobile | — | 05 Sections | not captured | Missing |
| Motion timings | motion/* | 01 Tokens | Estimated | Partial |

## Appendix — component CSS

```css
/* ===== Fourmula design system — copyable tokens + components (fm-) ===== */
:root{
  --fm-ink:#020108;--fm-ink-64:rgba(2,1,8,.64);--fm-ink-50:rgba(2,1,8,.5);--fm-ink-30:rgba(2,1,8,.3);--fm-ink-20:rgba(2,1,8,.2);
  --fm-white:#FFFFFF;--fm-white-50:rgba(255,255,255,.5);--fm-white-20:rgba(255,255,255,.2);
  --fm-surface:#FFFFFF;--fm-panel:#F7F7F7;--fm-line:#D7D7D6;--fm-menu:#272727;--fm-dark:#111111;--fm-line-dark:#2A2A30;--fm-dot:#D9D9D9;
  --fm-orange:#FA4A00;--fm-orange-2:#FC7404;
  --fm-g-orange:linear-gradient(180deg,#FA4A00 0%,#FB5A02 40%,#FC7404 100%);
  --fm-g-sky:linear-gradient(180deg,#48A3D0 0%,#85968C 35%,#C9965D 65%,#FC7404 100%);
  --fm-g-violet:linear-gradient(180deg,#3B56FF 0%,#8D6AAC 35%,#A86F80 60%,#FD7509 100%);
  --fm-g-crimson:linear-gradient(180deg,#9C0202 0%,#BC2A03 40%,#CB3F02 65%,#FC7404 100%);
  --fm-sans:"SF Pro Display","Inter",system-ui,-apple-system,sans-serif;
  --fm-r-sm:6.65px;--fm-r-md:12px;--fm-r-card:26.6px;--fm-r-panel:40px;--fm-r-pill:999px;
  --fm-s-1:6.65px;--fm-s-2:9.98px;--fm-s-3:13.3px;--fm-s-4:19.96px;--fm-s-5:26.6px;--fm-s-6:46.6px;--fm-s-7:66.5px;
  --fm-rail:406px;--fm-ease:cubic-bezier(.65,0,.35,1);
}
.fm-h2{font:400 99.8px/1 var(--fm-sans);letter-spacing:-.03em;color:var(--fm-ink);margin:0}
.fm-h1{font:400 73.2px/.94 var(--fm-sans);letter-spacing:-.03em;color:var(--fm-ink);margin:0}
.fm-h25{font:400 53.2px/1 var(--fm-sans);letter-spacing:-.03em;color:var(--fm-ink);margin:0}
.fm-h3{font:500 43.3px/1.05 var(--fm-sans);letter-spacing:-.03em;color:var(--fm-ink);margin:0}
.fm-title3{font:500 20px/1.5 var(--fm-sans);letter-spacing:-.01em}
.fm-body{font:400 15px/1.45 var(--fm-sans);letter-spacing:-.01em;color:var(--fm-ink)}
.fm-tag{font:400 15px/1.5 var(--fm-sans);color:var(--fm-ink)}
.fm-small{font:500 11.6px/1.3 var(--fm-sans);letter-spacing:-.01em;color:var(--fm-ink)}
.fm-micro{font:400 10px/1.5 var(--fm-sans);letter-spacing:-.01em;color:var(--fm-ink-50)}
.fm-mute{color:var(--fm-ink-50)}
.fm-btn{position:relative;display:inline-flex;align-items:center;justify-content:center;height:40px;padding:0 20px;border:0;border-radius:var(--fm-r-pill);background:var(--fm-ink);color:#fff;font:400 14.1px/17px var(--fm-sans);letter-spacing:-.02em;text-decoration:none;cursor:pointer;overflow:hidden}
.fm-btn span{display:block;transition:transform .45s var(--fm-ease)}
.fm-btn span+span{position:absolute;left:0;right:0;top:100%;text-align:center}
.fm-btn:hover span,.fm-btn:focus-visible span{transform:translateY(-100%)}
.fm-btn:focus-visible{outline:2px solid var(--fm-orange);outline-offset:2px}
.fm-btn--light{background:#fff;color:var(--fm-ink)}
.fm-btn--sm{height:26px;padding:0 12px;font-size:11px}
.fm-btn:disabled{background:var(--fm-panel);color:var(--fm-ink-30);cursor:not-allowed}
.fm-icon-btn{width:27px;height:27px;border-radius:50%;display:inline-grid;place-items:center;background:transparent;box-shadow:inset 0 0 0 1px var(--fm-ink-20);border:0;color:var(--fm-ink);cursor:pointer}
.fm-icon-btn svg{width:12px;height:12px}
.fm-pill{display:inline-flex;align-items:center;gap:10px;height:32px;padding:0 4px 0 12px;background:var(--fm-menu);border-radius:var(--fm-r-pill);color:#fff;font:400 14.1px var(--fm-sans);letter-spacing:-.02em}
.fm-burger{display:grid;gap:4px}.fm-burger i{display:block;width:18px;height:1.3px;background:#fff}
.fm-theme{width:24px;height:24px;border-radius:50%;display:grid;place-items:center;box-shadow:inset 0 0 0 1px var(--fm-white-20)}
.fm-progress{height:24px;padding:0 10px;border-radius:var(--fm-r-pill);background:var(--fm-white-20);display:inline-flex;align-items:center;font-size:13px}
.fm-label{font:500 11.6px var(--fm-sans);color:var(--fm-ink);display:inline-flex;align-items:center;gap:6px}
.fm-label::before{content:"";width:4px;height:4px;border-radius:50%;background:currentColor;opacity:.5}
.fm-bullet{font:500 10px var(--fm-sans);display:inline-flex;align-items:center;gap:8px;color:inherit}
.fm-bullet::before{content:"";width:4px;height:4px;background:currentColor}
.fm-paren{font:500 20px/1.5 var(--fm-sans);letter-spacing:-.01em;opacity:.4}
.fm-num{font:400 99.8px/1 var(--fm-sans);letter-spacing:-.03em}
.fm-plus{position:relative;width:12px;height:12px;flex:none}
.fm-plus::before,.fm-plus::after{content:"";position:absolute;background:var(--fm-ink)}
.fm-plus::before{left:5.5px;top:0;width:1px;height:12px}.fm-plus::after{top:5.5px;left:0;height:1px;width:12px}
.fm-faq[open] .fm-plus::before{display:none}
.fm-tile{width:110px;height:110px;border-radius:30%;background:#C9C3BA;transform:rotate(-28deg);overflow:hidden;display:grid;place-items:center}
.fm-tile i{width:70%;height:70%;border-radius:50%;background:linear-gradient(160deg,#7B6F63,#3E3833);transform:rotate(28deg)}
.fm-drop{width:88px;height:88px;border-radius:12px;background:#fff;box-shadow:inset 0 0 0 1px var(--fm-line);display:grid;place-items:center;color:var(--fm-ink-50)}
.fm-drop-cap{font:500 10.6px var(--fm-sans);text-align:center;margin-top:10px}
.fm-logo-tile{width:106px;height:84px;border-radius:var(--fm-r-sm);background:var(--fm-panel);display:grid;place-items:center;font:600 12px var(--fm-sans);color:#8A8A8A;letter-spacing:-.02em}
.fm-spin{width:18px;height:18px;border-radius:50%;background:conic-gradient(from 0deg,currentColor,transparent 70%);-webkit-mask:radial-gradient(circle,transparent 5px,#000 6px);mask:radial-gradient(circle,transparent 5px,#000 6px);animation:fmspin 1s linear infinite;color:var(--fm-ink-50)}
@keyframes fmspin{to{transform:rotate(1turn)}}
.fm-round{width:22px;height:22px;border-radius:50%;display:inline-grid;place-items:center;background:var(--fm-orange-2);color:#fff;border:0}
.fm-round--muted{background:rgba(255,255,255,.7);color:var(--fm-ink-64)}
.fm-round svg{width:11px;height:11px}
.fm-radio{width:12px;height:12px;border-radius:50%;box-shadow:inset 0 0 0 1px var(--fm-ink-20);background:#fff}
.fm-radio[aria-checked=true]{box-shadow:inset 0 0 0 3px #fff;background:var(--fm-orange-2);outline:1px solid var(--fm-orange-2)}
.fm-dot{width:10px;height:10px;border-radius:50%;background:var(--fm-dot)}
.fm-dot.on{background:var(--fm-ink)}
.fm-chip{display:inline-flex;align-items:center;gap:4px;height:22px;padding:0 8px;border-radius:var(--fm-r-pill);box-shadow:inset 0 0 0 1px var(--fm-orange-2);color:var(--fm-orange-2);font:500 11px var(--fm-sans)}
.fm-chip--fill{background:var(--fm-orange-2);color:#fff;box-shadow:none}
.fm-mark{display:inline-flex;align-items:center;gap:8px;font:600 18px var(--fm-sans);letter-spacing:-.03em;color:var(--fm-ink)}
.fm-mark i{width:16px;height:16px;background:var(--fm-ink);border-radius:2px}
/* molecules */
.fm-actions{display:inline-flex;align-items:center;gap:12px}
.fm-headblock{display:grid;gap:18px}
.fm-caption{display:grid;gap:12px;max-width:420px}
.fm-caption .fm-h3{font-size:30px}
.fm-bullets{display:grid;grid-template-columns:1fr 1fr;color:#fff}
.fm-bullets>div{padding:12px 13px;border-left:1px solid var(--fm-white-20);border-top:1px solid var(--fm-white-20)}
.fm-lead{display:grid;gap:18px;justify-items:start;color:#fff}
.fm-lead p{margin:0;font:500 14px/1.25 var(--fm-sans);letter-spacing:-.01em}
.fm-lead p span{color:var(--fm-white-50)}
.fm-word{font:400 58px/1 var(--fm-sans);letter-spacing:-.03em;padding:20px 20px 26px;border-bottom:1px solid var(--fm-line);color:var(--fm-ink)}
.fm-word--64{color:var(--fm-ink-64)}.fm-word--30{color:var(--fm-ink-30)}
.fm-faq{border-bottom:1px solid var(--fm-line)}
.fm-faq summary{list-style:none;display:flex;justify-content:space-between;align-items:center;gap:16px;padding:22px 20px;font:500 13.3px var(--fm-sans);letter-spacing:-.01em;cursor:pointer}
.fm-faq summary::-webkit-details-marker{display:none}
.fm-faq p{margin:0;padding:0 20px 22px;font:400 13.3px/1.5 var(--fm-sans);color:var(--fm-ink-64);max-width:560px}
.fm-face{position:relative;width:96px;height:112px;border-radius:var(--fm-r-md);background:linear-gradient(180deg,#EFEDEA,#D6CFC7 60%,#fff);overflow:hidden}
.fm-face.sel{box-shadow:0 0 0 2px var(--fm-orange-2)}
.fm-face .fm-radio{position:absolute;top:7px;left:7px}
.fm-face i{position:absolute;left:50%;bottom:-8px;width:58px;height:78px;border-radius:50% 50% 40% 40%;background:#9C8573;transform:translateX(-50%)}
.fm-result{position:relative;width:150px;height:140px;border-radius:var(--fm-r-md);background:linear-gradient(150deg,#C79B5B,#7A5428);overflow:hidden}
.fm-result .acts{position:absolute;top:8px;right:8px;display:flex;gap:4px}
.fm-result .cap{position:absolute;left:8px;bottom:6px;font:500 9px var(--fm-sans);color:#fff}
.fm-processing{width:150px;height:110px;border-radius:var(--fm-r-md);background:rgba(255,255,255,.18);display:grid;place-items:center;color:#fff}
.fm-toolbar{display:inline-flex;align-items:center;gap:6px;height:38px;padding:0 6px 0 12px;background:#fff;border-radius:var(--fm-r-pill)}
.fm-avatar{width:24px;height:24px;border-radius:50%;background:radial-gradient(circle at 40% 40%,#F3B49B,#B5321B)}
.fm-links{display:grid;gap:6px;font:500 10px var(--fm-sans);color:var(--fm-ink)}
.fm-links a{color:inherit;text-decoration:none}.fm-links a:hover{color:var(--fm-orange)}
.fm-consent{display:grid;gap:12px;max-width:300px;padding:18px;border-radius:var(--fm-r-card);background:#fff;box-shadow:inset 0 0 0 1px var(--fm-line)}
/* organisms */
.fm-header{display:flex;justify-content:space-between;align-items:center;gap:16px;flex-wrap:wrap}
.fm-orbit{position:relative;width:340px;height:300px;margin:auto}
.fm-orbit .fm-tile{position:absolute;width:64px;height:64px}
.fm-panel{background:var(--fm-panel);border-radius:var(--fm-r-panel);padding:28px}
.fm-glass{background:var(--fm-white-20);border-radius:var(--fm-r-card);padding:18px;display:grid;gap:12px}
.fm-glass h4{margin:0;font:500 16px var(--fm-sans);color:#fff}
.fm-slide{border-radius:0;background:var(--fm-g-orange);padding:22px;color:#fff;display:grid;gap:18px}
.fm-slide .top{display:flex;justify-content:space-between;align-items:flex-start}
.fm-slide .fm-h25{color:#fff;font-size:34px}
.fm-slide .fm-num{font-size:56px}
.fm-marquee{display:flex;gap:10px;overflow:hidden;-webkit-mask:linear-gradient(90deg,transparent,#000 12%,#000 88%,transparent);mask:linear-gradient(90deg,transparent,#000 12%,#000 88%,transparent)}
.fm-dots{display:grid;grid-template-columns:repeat(16,10px);gap:8px}
.fm-footer{background:var(--fm-panel);border-radius:var(--fm-r-panel);padding:24px;display:grid;gap:20px}
```
