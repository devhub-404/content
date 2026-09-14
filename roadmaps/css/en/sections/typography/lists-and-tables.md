# Styling Lists and Tables

List presentation can be controlled with `list-style-*`, `::marker`, and CSS counters while preserving HTML list semantics. Use CSS to change markers or numbering rather than replacing real lists with generic elements solely for visual control.

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

Tables have a specialized formatting model with border spacing/collapse, table layout, column sizing, and cell alignment. Style genuine tabular data rather than using tables for page layout. On narrow screens, a local horizontal scroll container often preserves row/column relationships better than changing table elements into unrelated block boxes.
