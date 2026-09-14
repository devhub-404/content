# Sizing Constraints and Intrinsic Sizes

`width`/`height` and logical `inline-size`/`block-size` express preferred sizes. `min-*` and `max-*` add lower and upper constraints, which compose well with responsive layout. Text containers usually need automatic block size so they can grow with content, zoom, localization, and user font settings.

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

Intrinsic sizes come from content. `min-content` approximates the smallest size allowed by wrapping rules, `max-content` the unwrapped preferred size, and `fit-content` uses intrinsic sizing while respecting available space. Flexbox and Grid use intrinsic contributions heavily; automatic minimum sizes are a common reason an item refuses to shrink until `min-inline-size: 0` or a `minmax(0, 1fr)` track is introduced.
