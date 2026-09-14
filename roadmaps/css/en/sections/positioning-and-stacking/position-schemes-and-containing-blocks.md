# Position Schemes and Containing Blocks

`position: static` keeps the normal positioning behavior. `relative` keeps the box in flow but allows visual offsets and commonly establishes a containing block for positioned descendants. `absolute` removes the box from normal flow and positions it using a containing block. `fixed` is usually viewport-relative, while `sticky` combines flow participation with scroll constraints.

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

Offsets such as `inset`, `top`, or logical inset properties make sense only after you know the containing block. Positioned ancestors commonly establish it, but transforms, containment, and other features can also affect the reference box. When an absolutely or fixed-positioned element appears in the wrong place, identify the containing block before changing numbers.
