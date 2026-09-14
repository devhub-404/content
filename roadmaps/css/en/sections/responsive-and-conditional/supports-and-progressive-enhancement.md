# Feature Queries and Progressive Enhancement

`@supports` tests whether the browser accepts a property/value or selector syntax and conditionally applies a block of CSS. It is useful when an enhancement needs coordinated rules. For a single property, normal fallback is often simpler: write the older valid declaration first and the newer declaration after it.

```css
.component {
  position: absolute;
  inset-block-start: 100%;
}

@supports (position-area: block-end) {
  .component {
    position-area: block-end;
  }
}
```

Progressive enhancement means the baseline remains usable while capable browsers receive better layout, visuals, or interaction. A parser accepting syntax does not guarantee every related browser behavior is bug-free, so critical features still need testing. Prefer standards-based fallbacks over browser sniffing and isolate newer features so they can be removed or expanded as your support baseline changes.
