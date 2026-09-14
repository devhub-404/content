# Compatibility, Progressive Delivery, and Debugging

CSS is a collection of modules with different specification maturity and browser adoption. A feature appearing in a specification does not mean every target browser supports the same syntax or sub-feature. Check compatibility for the exact feature you use and decide whether it is required, enhanced, or optional for your product.

```css
.component {
  display: block;
}

@supports (display: grid) {
  .component {
    display: grid;
  }
}
```

Build a robust baseline, add enhancements, and test both paths. In DevTools, debug in stages: selector matching, cascade winner, computed value, containing block, layout algorithm, overflow, stacking context, then paint/compositing. Randomly adding widths, `position`, large `z-index`, or `!important` can hide a symptom while leaving the underlying model wrong.
