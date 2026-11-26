# DESIGN.md — structure

The HTML guide exports this file. Keep the headings and order fixed so other agents, repos and tools can parse it. Codes (A-01, M-02, O-13, S-05, J-01) are the same as in the guide and in Figma.

````markdown
# [Brand] Design System

> Source: [URL or file] · captured [date] at [width × height] · method [DOM / screenshot / design file]
> Origin labels: Extracted · Estimated · Inferred · Generated · Source-specific · Updated

## 00 Overview
- Character: one paragraph (grounds, type pair, accent rule, depth model, texture)
- Grid: container, columns × width, gutter, margin, section height and rows
- Figma: page "Design System" → Sections 00 Source capture … 09 Coverage (only if built)

## 01 Tokens
### Color
| Token | Value | Use | Origin |
### Typography
| Style | Family / weight | Size / line height | Tracking | Case | Use |
### Spacing, sizes, grid
| Token | Value | Origin |
### Radius, effects, motion
| Token | Value | Origin |
### CSS
```css
:root{ --token: value; … }
```

## 02 Atoms
### A-01 Button / Light
- Made of: tokens (list)
- States: Default · Hover · Focus · Disabled
- Origin: Extracted (states Generated where noted)
```html
<button class="ob-btn">Label</button>
```
(repeat for every atom)

## 03 Molecules
### M-01 Section tag
- Made of: A-06 + A-07
```html
…
```

## 04 Organisms
| Code | Organism | Anatomy in visual order | Made of |
### O-01 Header
```html
…
```

## 05 Sections & templates
| Code | Section | Ground | Height | Uses |
### T-01 Centered template · T-02 Split template (slots)

## 06 Pages
- Home: S-01 → S-02 → … → S-12 (total height, split points)

## 07 Flows
- J-01 Discover → book: S-01 → S-02 → … → A-03 → S-12
- J-02 …

## 08 Product & rules
### Experience
### Take vs leave
| Take (structure) | Leave (source-specific) |
### Usage rules
| Topic | Rule |
### Limitations
### Changelog

## 09 Coverage
### Totals
| Level | Count |
### Matrix
| Item | Code | Level | Location | Status |

## Appendix — component CSS
```css
/* full #ds block */
```
````
