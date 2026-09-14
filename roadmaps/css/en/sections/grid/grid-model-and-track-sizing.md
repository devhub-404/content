# Grid Tracks, Lines, and `fr`

Grid is a two-dimensional layout system. Columns and rows are tracks separated by grid lines; the intersection of one row and column is a cell, and an item can span several cells. Direct children of a grid container become grid items. Explicit tracks come from the template; placement can also create implicit tracks.

```css
.layout {
  display: grid;
  grid-template-columns: 16rem 1fr;
  grid-template-rows: auto 1fr;
  gap: 1rem;
}
```

`fr` distributes flexible leftover space after fixed sizes, gaps, and intrinsic contributions are considered. It is not simply a percentage. Content-based minimums can make a `1fr` track larger than expected; `minmax(0, 1fr)` is useful when you explicitly want a track to shrink below its content minimum.
