# Scroll Alignment, Snap, Overscroll, and Scrollbars

`scroll-padding` reserves an optimal viewing inset inside a scroll container, while `scroll-margin` expands a target's alignment area. They are useful for fragment links and focus targets that would otherwise land behind sticky UI. Scroll snap defines preferred resting positions with container `scroll-snap-type` and item `scroll-snap-align`.

```css
html {
  scroll-padding-block-start: 5rem;
}

.carousel {
  display: flex;
  overflow-x: auto;
  scroll-snap-type: inline mandatory;
  overscroll-behavior-inline: contain;
}

.carousel > * {
  scroll-snap-align: start;
}
```

`overscroll-behavior` controls scroll chaining at boundaries. Scrollbar styling offers limited width/color control but should preserve discoverability and operating-system preferences. Avoid mandatory snapping in long reading surfaces and avoid hiding scrollbars merely for visual cleanliness. Scrollable regions must remain usable with pointer, touch, keyboard, and assistive navigation.
