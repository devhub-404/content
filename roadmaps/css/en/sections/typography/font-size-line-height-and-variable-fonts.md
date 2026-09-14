# Font Size, Line Height, and Variable Fonts

Readable typography needs appropriate font size, line height, and measure. Unitless `line-height` scales with each element's own font size and is usually robust for inherited body typography. Headings often use tighter line height because they are larger and shorter. Keep body text scalable and test zoom rather than locking type to fixed pixels.

```css
body {
  font-size: 1rem;
  line-height: 1.6;
}

h1 {
  font-size: clamp(2rem, 5vw, 4rem);
  line-height: 1.1;
  font-weight: 650;
  font-optical-sizing: auto;
}
```

Variable fonts can expose ranges such as weight, width, slant, and optical size. Prefer high-level properties like `font-weight`, `font-stretch`, and `font-optical-sizing` when they map to the axis you need. Low-level `font-variation-settings` is useful for custom axes, but the font file must actually provide the requested axis and range.
