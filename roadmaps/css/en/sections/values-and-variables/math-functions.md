# CSS Math Functions

`calc()` combines compatible numeric expressions, including values with different units. `min()` chooses the smallest candidate, `max()` the largest, and `clamp(min, preferred, max)` bounds a preferred value. These functions let CSS express constraints directly instead of simulating every intermediate size with breakpoints.

```css
main {
  inline-size: min(70rem, calc(100% - 2rem));
  margin-inline: auto;
}

h1 {
  font-size: clamp(2rem, 5vw, 4rem);
}
```

Fluid sizing is useful when the relationship is continuous, such as spacing or type that should grow within reasonable limits. It does not replace conditional rules for layout mode changes. If a sidebar should move below the main content, that is a discrete layout decision and belongs in a media or container query rather than an increasingly complicated `calc()` expression.
