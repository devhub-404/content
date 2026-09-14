# Flex Containers, Items, and Axes

`display: flex` or `inline-flex` makes direct children flex items. Flexbox is one-dimensional: it lays items along a main axis and aligns them on a cross axis. `flex-direction` selects the main axis, with `row`, `row-reverse`, `column`, and `column-reverse` values that follow writing mode and direction.

```css
.toolbar {
  display: flex;
  align-items: center;
  gap: .75rem;
}
```

Think in main/cross axes rather than hard-coding “horizontal” and “vertical.” Flexbox is a strong fit for toolbars, navigation, button groups, media objects, and other layouts where one dimension is the primary relationship. Only direct children become flex items; deeper descendants keep their own formatting context unless another rule changes it.
