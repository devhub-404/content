---
locale: en
status: published
title: "CSS"
slug: css
description: "A task-oriented quick reference for everyday CSS syntax, APIs, and workflows."
tags:
  - css
  - cheatsheet
  - quick-reference
references:
  - label: "MDN: CSS"
    url: https://developer.mozilla.org/en-US/docs/Web/CSS
  - label: "MDN: CSS cascade"
    url: https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Cascade
  - label: "MDN: Flexible box layout"
    url: https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Flexible_box_layout
---

# CSS

Task-oriented quick reference. Search the page and copy the smallest example that matches what you need.

## CSS Language & Cascade

**CSS Rules and Stylesheets**

```css
p {
  color: navy;
  font-size: 1.1rem;
}
```

**Declarations, Values, Functions, and At-rules**

```css
@media (width >= 48rem) {
  .card {
    width: min(40rem, 100%);
    color: rgb(20 30 50 / 0.9);
  }
}
```

**Shorthands and Resets**

```css
.card {
  margin: 1rem 2rem;
  border: 1px solid #ccc;
  background: white;
}
```

**How the Cascade Chooses a Value**

```css
.message { color: navy; }
.message { color: rebeccapurple; }
```

**Specificity and Inheritance**

```css
p { color: black; }
.note { color: navy; }
#warning { color: crimson; }

article {
  color: #333;
  font-family: system-ui;
}
```

**Layers, Scope, and `!important`**

```css
@layer reset, base, components, utilities;

@layer components {
  .button { padding: .6rem 1rem; }
}

@layer utilities {
  .p-0 { padding: 0; }
}

@scope (.article) {
  a { color: #2457d6; }
}
```

**Native CSS Nesting**

```css
.card {
  padding: 1rem;

  > h2 {
    margin-block-start: 0;
  }

  &:hover {
    border-color: #888;
  }

  @media (width >= 40rem) {
    padding: 1.5rem;
  }
}
```

## Selectors

**Type, Class, ID, and Universal Selectors**

```css
p { color: #333; }
.note { background: #fff8c5; }
#main-title { letter-spacing: -.02em; }
* { box-sizing: border-box; }
```

**Combinators**

```css
article p { color: #333; }
article > p { max-inline-size: 68ch; }
h2 + p { margin-block-start: 0; }
h2 ~ p { color: #444; }
```

**Attribute and State Selectors**

```css
input[required] { border-inline-start-width: 3px; }
input[type="email"] { inline-size: 24rem; }
a[href^="https:"] { text-decoration-style: dotted; }

button:hover { filter: brightness(1.05); }
button:focus-visible { outline: 3px solid currentColor; }
input:checked + label { font-weight: 700; }
```

**Structural Pseudo-classes**

```css
li:first-child { margin-block-start: 0; }
tr:nth-child(even) { background: rgb(0 0 0 / .04); }
.card:nth-child(-n + 3 of .featured) { border-width: 2px; }
```

**`:is()`, `:where()`, `:not()`, and `:has()`**

```css
article :is(h2, h3, h4) { line-height: 1.2; }
:where(article, section) > p { max-inline-size: 68ch; }
button:not(:disabled) { cursor: pointer; }
.card:has(img) { grid-template-columns: 8rem 1fr; }
```

**Pseudo-elements and Generated Content**

```css
.tag::before {
  content: "#";
  opacity: .6;
}

li::marker { font-weight: 700; }

::selection {
  background: Highlight;
  color: HighlightText;
}
```

## Values, Units & Variables

**Numbers, Dimensions, and Percentages**

```css
.box {
  inline-size: 20rem;
  rotate: 5deg;
  transition-duration: 200ms;
  opacity: .8;
  max-inline-size: 80%;
}
```

**Font-, Viewport-, and Container-relative Units**

```css
.prose { max-inline-size: 68ch; }
.button { padding: .65em 1em; }
.hero { min-block-size: 100svh; }

.card-shell { container-type: inline-size; }
.card h2 { font-size: clamp(1.2rem, 5cqi, 2rem); }
```

**CSS Math Functions**

```css
main {
  inline-size: min(70rem, calc(100% - 2rem));
  margin-inline: auto;
}

h1 {
  font-size: clamp(2rem, 5vw, 4rem);
}
```

**Custom Properties and `var()`**

```css
:root {
  --surface: white;
  --text: #161616;
  --space-card: 1rem;
}

.card {
  color: var(--text);
  background: var(--surface);
  padding: var(--space-card, 1rem);
}

[data-theme="dark"] {
  --surface: #161616;
  --text: white;
}
```

**Registered Custom Properties with `@property`**

```css
@property --progress {
  syntax: "<number>";
  inherits: false;
  initial-value: 0;
}

.bar {
  --progress: .65;
  scale: var(--progress) 1;
}
```

## Box Model, Flow & Logical Layout

**The Box Model and `box-sizing`**

```css
*,
*::before,
*::after {
  box-sizing: border-box;
}

.card {
  inline-size: 20rem;
  padding: 1rem;
  border: 1px solid #ccc;
  margin-block: 1rem;
}
```

**Sizing Constraints and Intrinsic Sizes**

```css
.article {
  inline-size: 100%;
  max-inline-size: 70rem;
}

.label {
  inline-size: fit-content;
}

.grid {
  grid-template-columns: minmax(0, 1fr) max-content;
}
```

**`display` and Normal Flow**

```css
.badge { display: inline-block; }
.toolbar { display: flex; }
.gallery { display: grid; }
.wrapper { display: flow-root; }
```

**Margin Collapsing and Block Formatting Contexts**

```css
.stack > * + * {
  margin-block-start: 1rem;
}

.isolated {
  display: flow-root;
}
```

**Overflow and Scroll Containers**

```css
.code-frame {
  max-inline-size: 100%;
  overflow: auto;
}

.long-token {
  overflow-wrap: anywhere;
}
```

**Writing Modes and Logical Properties**

```css
.card {
  inline-size: min(100%, 40rem);
  padding-block: 1rem;
  padding-inline: 1.25rem;
}

.badge {
  inset-block-start: .5rem;
  inset-inline-end: .5rem;
}
```

## Positioning & Stacking

**Position Schemes and Containing Blocks**

```css
.card {
  position: relative;
}

.card__badge {
  position: absolute;
  inset-block-start: .5rem;
  inset-inline-end: .5rem;
}
```

**Sticky Positioning**

```css
.section-title {
  position: sticky;
  inset-block-start: 0;
  background: Canvas;
  z-index: 1;
}
```

**Stacking Contexts and `z-index`**

```css
:root {
  --z-sticky: 10;
  --z-overlay: 100;
  --z-modal: 110;
}

.site-header {
  position: sticky;
  z-index: var(--z-sticky);
}
```

**Anchor Positioning**

```css
.trigger {
  anchor-name: --menu-trigger;
}

.menu {
  position: absolute;
  position-anchor: --menu-trigger;
  position-area: block-end span-inline-end;
}
```

## Flexible Box Layout

**Flex Containers, Items, and Axes**

```css
.toolbar {
  display: flex;
  align-items: center;
  gap: .75rem;
}
```

**Flex Basis, Grow, Shrink, and Minimum Size**

```css
.sidebar {
  flex: 0 0 16rem;
}

.main {
  flex: 1 1 0;
  min-inline-size: 0;
}
```

**Flex Alignment, Gaps, and Auto Margins**

```css
.nav {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.nav__account {
  margin-inline-start: auto;
}
```

**Wrapping and Visual Order**

```css
.chips {
  display: flex;
  flex-wrap: wrap;
  gap: .5rem;
}

.featured {
  order: -1;
}
```

## Grid Layout

**Grid Tracks, Lines, and `fr`**

```css
.layout {
  display: grid;
  grid-template-columns: 16rem 1fr;
  grid-template-rows: auto 1fr;
  gap: 1rem;
}
```

**`repeat()`, `minmax()`, and Auto-fit Grids**

```css
.cards {
  display: grid;
  grid-template-columns:
    repeat(auto-fit, minmax(min(16rem, 100%), 1fr));
  gap: 1rem;
}
```

**Grid Placement, Spans, and Areas**

```css
.page {
  display: grid;
  grid-template:
    "header header" auto
    "sidebar main" 1fr
    / 16rem 1fr;
}

header { grid-area: header; }
aside  { grid-area: sidebar; }
main   { grid-area: main; }

.wide { grid-column: 1 / -1; }
```

**Auto-placement, Alignment, and Subgrid**

```css
.gallery {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-auto-rows: 10rem;
}

.card {
  display: grid;
  grid-template-rows: subgrid;
  grid-row: span 3;
}
```

## Typography & Text

**Font Families and Web Fonts**

```css
body {
  font-family: Inter, system-ui, sans-serif;
}

@font-face {
  font-family: "Brand Sans";
  src: url("/fonts/brand-sans.woff2") format("woff2");
  font-weight: 100 900;
  font-style: normal;
  font-display: swap;
}
```

**Font Size, Line Height, and Variable Fonts**

```css
body {
  font-size: 1rem;
  line-height: 1.6;
}

h1 {
  font-size: clamp(2rem, 5vw, 4rem);
  line-height: 1.1;
  font-weight: 650;
  font-optical-sizing: auto;
}
```

**Whitespace, Wrapping, and Hyphenation**

```css
.prose {
  max-inline-size: 68ch;
  hyphens: auto;
}

.long-token {
  overflow-wrap: anywhere;
}

pre {
  white-space: pre-wrap;
}
```

**Text Alignment and Decoration**

```css
.article {
  text-align: start;
}

.article a {
  text-decoration-thickness: .08em;
  text-underline-offset: .18em;
}
```

**Styling Lists and Tables**

```css
li::marker {
  color: #2457d6;
  font-weight: 700;
}

table {
  border-collapse: collapse;
  inline-size: 100%;
}

th,
td {
  padding: .75rem;
  text-align: start;
}
```

## Color, Backgrounds & Visual Effects

**Colors, Alpha, and `currentColor`**

```css
.button {
  color: oklch(52% .2 255);
  border: 1px solid currentColor;
  background: rgb(255 255 255 / .9);
}
```

**Background Layers and Gradients**

```css
.hero {
  background:
    linear-gradient(rgb(0 0 0 / .55), rgb(0 0 0 / .15)),
    url("/images/hero.jpg") center / cover no-repeat;
  color: white;
}
```

**Borders, Radius, Outlines, and Shadows**

```css
.card {
  border: 1px solid rgb(0 0 0 / .15);
  border-radius: 1rem;
  box-shadow: 0 .75rem 2rem rgb(0 0 0 / .18);
}

.card :focus-visible {
  outline: 3px solid Highlight;
  outline-offset: 3px;
}
```

**Replaced Elements and Object Fitting**

```css
.thumbnail {
  inline-size: 100%;
  aspect-ratio: 16 / 9;
  object-fit: cover;
  object-position: 50% 35%;
}
```

**Filters, Clipping, Masking, and Blending**

```css
.photo { filter: saturate(.9) contrast(1.05); }
.avatar { clip-path: circle(45%); }

.fade-edge {
  mask-image:
    linear-gradient(to right, transparent, black 15%, black 85%, transparent);
}
```

**Color Schemes and Forced Colors**

```css
:root {
  color-scheme: light dark;
}

.alert {
  border: 2px solid currentColor;
}

@media (forced-colors: active) {
  .alert {
    forced-color-adjust: auto;
  }
}
```

## Responsive & Conditional CSS

**Responsive Layout Before Breakpoints**

```css
.page {
  inline-size: min(72rem, calc(100% - 2rem));
  margin-inline: auto;
}

img {
  max-inline-size: 100%;
  block-size: auto;
}
```

**Media Queries and Range Syntax**

```css
@media (width >= 48rem) {
  .layout {
    display: grid;
    grid-template-columns: 1fr 18rem;
  }
}

@media (40rem <= width < 70rem) {
  .toolbar { gap: .5rem; }
}
```

**User Preference and Input Capability Queries**

```css
@media (prefers-reduced-motion: reduce) {
  .panel { transition: none; }
}

@media (prefers-color-scheme: dark) {
  :root { --surface: #161616; --text: #f5f5f5; }
}

@media (hover: hover) and (pointer: fine) {
  .menu-item:hover { text-decoration: underline; }
}
```

**Container Queries and Container Units**

```css
.card-shell {
  container: card / inline-size;
}

@container card (width >= 32rem) {
  .card {
    display: grid;
    grid-template-columns: 10rem 1fr;
  }
}

.card h2 {
  font-size: clamp(1.2rem, 5cqi, 2rem);
}
```

**Feature Queries and Progressive Enhancement**

```css
.component {
  position: absolute;
  inset-block-start: 100%;
}

@supports (position-area: block-end) {
  .component {
    position-area: block-end;
  }
}
```

## UI, Scrolling & Motion

**Form Controls, Focus, and Accent Color**

```css
input,
button,
select,
textarea {
  font: inherit;
}

input[type="checkbox"],
input[type="radio"] {
  accent-color: #2457d6;
}

:focus-visible {
  outline: 3px solid Highlight;
  outline-offset: 3px;
}
```

**Scroll Alignment, Snap, Overscroll, and Scrollbars**

```css
html {
  scroll-padding-block-start: 5rem;
}

.carousel {
  display: flex;
  overflow-x: auto;
  scroll-snap-type: inline mandatory;
  overscroll-behavior-inline: contain;
}

.carousel > * {
  scroll-snap-align: start;
}
```

**Transforms**

```css
.badge {
  translate: 0 -.15em;
  rotate: -2deg;
}

.button:active {
  scale: .98;
}
```

**Transitions and Starting Styles**

```css
.button {
  background: #2457d6;
  translate: 0 0;
  transition:
    background 150ms ease,
    translate 150ms ease;
}

.button:hover {
  background: #1749bd;
  translate: 0 -2px;
}
```

**Keyframes, Easing, and Reduced Motion**

```css
@keyframes pulse {
  0%, 100% { scale: 1; }
  50% { scale: 1.04; }
}

.busy {
  animation: pulse 1.2s ease-in-out infinite;
}

@media (prefers-reduced-motion: reduce) {
  .busy { animation: none; }
}
```

**Scroll-driven Animations and View Transitions**

```css
.reading-progress {
  transform-origin: left;
  animation: grow linear both;
  animation-timeline: scroll(root block);
}

@keyframes grow {
  from { scale: 0 1; }
  to   { scale: 1 1; }
}

.product-card {
  view-transition-name: selected-product;
}
```

## Architecture, Compatibility & Performance

**Design Tokens and Theme Architecture**

```css
@layer tokens {
  :root {
    --color-blue-600: oklch(52% .2 255);
    --color-surface: white;
    --color-action: var(--color-blue-600);
    --space-card: 1rem;
  }

  [data-theme="dark"] {
    --color-surface: #151515;
  }
}
```

**Containment and `content-visibility`**

```css
.widget {
  contain: layout paint;
}

.feed-item {
  content-visibility: auto;
  contain-intrinsic-size: auto 24rem;
}
```

**`will-change` and Rendering Performance**

```css
.dragging {
  will-change: transform;
}

/* Remove the hint when the interaction ends. */
```

**Compatibility, Progressive Delivery, and Debugging**

```css
.component {
  display: block;
}

@supports (display: grid) {
  .component {
    display: grid;
  }
}
```
