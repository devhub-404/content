# Declarations, Values, Functions, and At-rules

A declaration is a property followed by a value. Values can be keywords, numbers, dimensions, percentages, colors, URLs, images, functions, or combinations defined by that property's grammar. Functions such as `min()`, `calc()`, `rgb()`, and `var()` are value syntax; they are not JavaScript calls.

```css
@media (width >= 48rem) {
  .card {
    width: min(40rem, 100%);
    color: rgb(20 30 50 / 0.9);
  }
}
```

At-rules begin with `@` and introduce behavior larger than one declaration. Some wrap rules, such as `@media`, `@supports`, `@container`, `@layer`, and `@scope`; others define resources or timelines, such as `@font-face` and `@keyframes`. CSS is error-tolerant: an unknown or invalid declaration is normally ignored while surrounding valid CSS continues.
