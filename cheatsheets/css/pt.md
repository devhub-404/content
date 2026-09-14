---
locale: pt
status: published
title: "CSS"
slug: css
description: "Uma referência rápida orientada a tarefas para sintaxe, APIs e workflows cotidianos de CSS."
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

Referência rápida orientada a tarefas. Pesquise na página e copie o menor exemplo que corresponde ao que você precisa.

## Linguagem CSS e Cascata

**Regras CSS e Folhas de Estilo**

```css
p {
  color: navy;
  font-size: 1.1rem;
}
```

**Declarações, Valores, Funções e At-rules**

```css
@media (width >= 48rem) {
  .card {
    width: min(40rem, 100%);
    color: rgb(20 30 50 / 0.9);
  }
}
```

**Shorthands e Resets**

```css
.card {
  margin: 1rem 2rem;
  border: 1px solid #ccc;
  background: white;
}
```

**Como a Cascata Escolhe um Valor**

```css
.message { color: navy; }
.message { color: rebeccapurple; }
```

**Especificidade e Herança**

```css
p { color: black; }
.note { color: navy; }
#warning { color: crimson; }

article {
  color: #333;
  font-family: system-ui;
}
```

**Layers, Scope e `!important`**

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

**Nesting Nativo do CSS**

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

## Seletores

**Seletores de Tipo, Classe, ID e Universal**

```css
p { color: #333; }
.note { background: #fff8c5; }
#main-title { letter-spacing: -.02em; }
* { box-sizing: border-box; }
```

**Combinadores**

```css
article p { color: #333; }
article > p { max-inline-size: 68ch; }
h2 + p { margin-block-start: 0; }
h2 ~ p { color: #444; }
```

**Seletores de Atributo e Estado**

```css
input[required] { border-inline-start-width: 3px; }
input[type="email"] { inline-size: 24rem; }
a[href^="https:"] { text-decoration-style: dotted; }

button:hover { filter: brightness(1.05); }
button:focus-visible { outline: 3px solid currentColor; }
input:checked + label { font-weight: 700; }
```

**Pseudo-classes Estruturais**

```css
li:first-child { margin-block-start: 0; }
tr:nth-child(even) { background: rgb(0 0 0 / .04); }
.card:nth-child(-n + 3 of .featured) { border-width: 2px; }
```

**`:is()`, `:where()`, `:not()` e `:has()`**

```css
article :is(h2, h3, h4) { line-height: 1.2; }
:where(article, section) > p { max-inline-size: 68ch; }
button:not(:disabled) { cursor: pointer; }
.card:has(img) { grid-template-columns: 8rem 1fr; }
```

**Pseudo-elementos e Conteúdo Gerado**

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

## Valores, Unidades e Variáveis

**Números, Dimensões e Porcentagens**

```css
.box {
  inline-size: 20rem;
  rotate: 5deg;
  transition-duration: 200ms;
  opacity: .8;
  max-inline-size: 80%;
}
```

**Unidades Relativas a Fonte, Viewport e Container**

```css
.prose { max-inline-size: 68ch; }
.button { padding: .65em 1em; }
.hero { min-block-size: 100svh; }

.card-shell { container-type: inline-size; }
.card h2 { font-size: clamp(1.2rem, 5cqi, 2rem); }
```

**Funções Matemáticas do CSS**

```css
main {
  inline-size: min(70rem, calc(100% - 2rem));
  margin-inline: auto;
}

h1 {
  font-size: clamp(2rem, 5vw, 4rem);
}
```

**Custom Properties e `var()`**

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

**Custom Properties Registradas com `@property`**

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

## Box Model, Fluxo e Layout Lógico

**Box Model e `box-sizing`**

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

**Restrições de Tamanho e Tamanhos Intrínsecos**

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

**`display` e Fluxo Normal**

```css
.badge { display: inline-block; }
.toolbar { display: flex; }
.gallery { display: grid; }
.wrapper { display: flow-root; }
```

**Colapso de Margens e Block Formatting Contexts**

```css
.stack > * + * {
  margin-block-start: 1rem;
}

.isolated {
  display: flow-root;
}
```

**Overflow e Scroll Containers**

```css
.code-frame {
  max-inline-size: 100%;
  overflow: auto;
}

.long-token {
  overflow-wrap: anywhere;
}
```

**Writing Modes e Propriedades Lógicas**

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

## Posicionamento e Empilhamento

**Esquemas de Posição e Containing Blocks**

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

**Posicionamento Sticky**

```css
.section-title {
  position: sticky;
  inset-block-start: 0;
  background: Canvas;
  z-index: 1;
}
```

**Stacking Contexts e `z-index`**

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

**Flex Containers, Itens e Eixos**

```css
.toolbar {
  display: flex;
  align-items: center;
  gap: .75rem;
}
```

**Flex Basis, Grow, Shrink e Tamanho Mínimo**

```css
.sidebar {
  flex: 0 0 16rem;
}

.main {
  flex: 1 1 0;
  min-inline-size: 0;
}
```

**Alinhamento Flex, Gaps e Margens Auto**

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

**Quebra de Linha e Ordem Visual**

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

**Tracks, Linhas e `fr` no Grid**

```css
.layout {
  display: grid;
  grid-template-columns: 16rem 1fr;
  grid-template-rows: auto 1fr;
  gap: 1rem;
}
```

**`repeat()`, `minmax()` e Grids com Auto-fit**

```css
.cards {
  display: grid;
  grid-template-columns:
    repeat(auto-fit, minmax(min(16rem, 100%), 1fr));
  gap: 1rem;
}
```

**Placement, Spans e Áreas no Grid**

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

**Auto-placement, Alinhamento e Subgrid**

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

## Tipografia e Texto

**Famílias de Fonte e Web Fonts**

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

**Tamanho de Fonte, Line Height e Fontes Variáveis**

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

**Whitespace, Quebra e Hifenização**

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

**Alinhamento e Decoração de Texto**

```css
.article {
  text-align: start;
}

.article a {
  text-decoration-thickness: .08em;
  text-underline-offset: .18em;
}
```

**Estilizando Listas e Tabelas**

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

## Cor, Backgrounds e Efeitos Visuais

**Cores, Alpha e `currentColor`**

```css
.button {
  color: oklch(52% .2 255);
  border: 1px solid currentColor;
  background: rgb(255 255 255 / .9);
}
```

**Camadas de Background e Gradientes**

```css
.hero {
  background:
    linear-gradient(rgb(0 0 0 / .55), rgb(0 0 0 / .15)),
    url("/images/hero.jpg") center / cover no-repeat;
  color: white;
}
```

**Bordas, Radius, Outlines e Shadows**

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

**Elementos Substituídos e Object Fitting**

```css
.thumbnail {
  inline-size: 100%;
  aspect-ratio: 16 / 9;
  object-fit: cover;
  object-position: 50% 35%;
}
```

**Filters, Clipping, Masking e Blending**

```css
.photo { filter: saturate(.9) contrast(1.05); }
.avatar { clip-path: circle(45%); }

.fade-edge {
  mask-image:
    linear-gradient(to right, transparent, black 15%, black 85%, transparent);
}
```

**Color Schemes e Forced Colors**

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

## CSS Responsivo e Condicional

**Layout Responsivo Antes de Breakpoints**

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

**Media Queries e Sintaxe de Range**

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

**Queries de Preferência do Usuário e Capacidade de Entrada**

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

**Container Queries e Unidades de Container**

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

**Feature Queries e Progressive Enhancement**

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

## UI, Scrolling e Movimento

**Controles de Formulário, Foco e Accent Color**

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

**Alinhamento de Scroll, Snap, Overscroll e Scrollbars**

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

**Transitions e Starting Styles**

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

**Keyframes, Easing e Movimento Reduzido**

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

**Animações por Scroll e View Transitions**

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

## Arquitetura, Compatibilidade e Performance

**Design Tokens e Arquitetura de Tema**

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

**Containment e `content-visibility`**

```css
.widget {
  contain: layout paint;
}

.feed-item {
  content-visibility: auto;
  contain-intrinsic-size: auto 24rem;
}
```

**`will-change` e Performance de Rendering**

```css
.dragging {
  will-change: transform;
}

/* Remove the hint when the interaction ends. */
```

**Compatibilidade, Entrega Progressiva e Depuração**

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
