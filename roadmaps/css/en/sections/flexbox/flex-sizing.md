# Flex Basis, Grow, Shrink, and Minimum Size

Flex sizing starts from each item's flex base size, commonly controlled by `flex-basis`. Positive free space can be distributed according to `flex-grow`; negative free space participates in `flex-shrink`. The `flex` shorthand is usually clearer because grow, shrink, and basis form one sizing policy.

```css
.sidebar {
  flex: 0 0 16rem;
}

.main {
  flex: 1 1 0;
  min-inline-size: 0;
}
```

Flex items also have an automatic minimum size that can preserve long content. That is why a main content item can overflow even though it is allowed to shrink; `min-inline-size: 0` often expresses that the item may become narrower than its content's intrinsic minimum. `flex: 1` is shorthand behavior, not simply “one fraction of width.”
