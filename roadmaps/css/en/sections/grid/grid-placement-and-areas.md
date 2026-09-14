# Grid Placement, Spans, and Areas

Grid placement is line-based. Items can be placed with numbered lines, named lines, `span`, or named template areas. Negative line numbers count from the end of the explicit grid, which makes `1 / -1` a useful full-span pattern. Template areas make page-region layouts readable as long as each named area forms a rectangle.

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

Explicit placement changes visual position, not source order. Keep the DOM in a meaningful reading and focus sequence even if the grid places regions elsewhere visually. Use placement when geometry itself is the requirement; do not rearrange semantic order simply because Grid makes it easy.
