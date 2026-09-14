# Shorthands and Resets

Shorthand properties set several related longhands at once. `margin`, `padding`, `border`, `background`, `font`, `flex`, `grid`, `transition`, and `animation` are common examples. They make intent concise when you are describing the whole group.

```css
.card {
  margin: 1rem 2rem;
  border: 1px solid #ccc;
  background: white;
}
```

A shorthand can also reset longhands you did not explicitly mention. Replacing `background-color` later with a `background` shorthand can reset background image, position, repeat, and other sub-properties. Use shorthands deliberately and inspect computed styles when an earlier longhand appears to vanish. CSS-wide keywords such as `initial`, `inherit`, `unset`, `revert`, and `revert-layer` provide different kinds of reset.
