# Wrapping and Visual Order

`flex-wrap: wrap` lets items form additional flex lines when one line cannot fit. Each line is laid out independently, so wrapped items do not create shared columns across lines. If aligned rows and columns matter together, Grid is usually the stronger model.

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

`order`, `row-reverse`, and `column-reverse` can change visual order without normally changing DOM reading or keyboard focus order. Use them only when the semantic sequence remains sensible. If meaningful content needs to appear first, fix the source order rather than relying on CSS to present one story visually and another to keyboard or assistive-technology users.
