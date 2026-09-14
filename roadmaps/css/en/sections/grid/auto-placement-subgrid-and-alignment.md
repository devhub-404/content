# Auto-placement, Alignment, and Subgrid

Unpositioned grid items use the auto-placement algorithm. `grid-auto-flow` controls row- or column-oriented placement, while `grid-auto-rows` and `grid-auto-columns` size implicit tracks. Dense packing can backfill holes but may make visual order diverge from source order, so use it cautiously.

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

Grid uses the Box Alignment properties for item alignment and track distribution. `subgrid` lets a nested grid reuse parent track sizing on one or both axes, which is valuable when repeated cards should align titles, bodies, or footers across siblings. Use an independent nested grid when the child should own its geometry; use subgrid when ancestor track alignment is the actual relationship.
