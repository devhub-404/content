# Media Queries and Range Syntax

`@media` conditionally applies rules based on media features such as viewport width/height, orientation, resolution, display mode, color capability, and user preferences. Modern comparison syntax expresses ranges directly and can be clearer than older `min-*`/`max-*` forms.

```css
@media (width >= 48rem) {
  .layout {
    display: grid;
    grid-template-columns: 1fr 18rem;
  }
}

@media (40rem <= width < 70rem) {
  .toolbar { gap: .5rem; }
}
```

Keep the simpler layout outside the query when that creates a robust baseline, then enhance it at conditions where another arrangement becomes useful. Do not create a breakpoint for every small visual difference. If a rule truly depends on the size of a reusable component rather than the viewport, use a container query instead.
