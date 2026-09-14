# Transitions and Starting Styles

A transition interpolates an animatable property when its computed value changes. Specify the properties you intend to animate instead of `transition: all`, because future unrelated changes can otherwise start animating unexpectedly. Duration, timing function, and delay control the progression.

```css
.button {
  background: #2457d6;
  translate: 0 0;
  transition:
    background 150ms ease,
    translate 150ms ease;
}

.button:hover {
  background: #1749bd;
  translate: 0 -2px;
}
```

`@starting-style` can provide a starting value for entry transitions when a newly rendered state did not previously have one, such as an opening popover. Keep the static start/end states correct without animation. Opacity and transforms are often efficient animation targets, but measure real rendering when performance matters rather than assuming every transform is automatically cheap.
