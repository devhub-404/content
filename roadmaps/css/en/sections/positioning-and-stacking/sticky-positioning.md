# Sticky Positioning

A sticky box remains in normal flow until scrolling would move it past a specified inset threshold, then it is constrained relative to its scrollport. It needs a relevant inset such as `inset-block-start`; without a threshold, there is nothing to stick against.

```css
.section-title {
  position: sticky;
  inset-block-start: 0;
  background: Canvas;
  z-index: 1;
}
```

Ancestor overflow matters because a scrolling ancestor can become the relevant scroll container. Sticky headers also need a deliberate background and stacking behavior so content underneath does not become unreadable. Because the element still occupies its normal-flow space, sticky positioning is usually easier to integrate than a fixed header when the goal is local persistence during scrolling.
