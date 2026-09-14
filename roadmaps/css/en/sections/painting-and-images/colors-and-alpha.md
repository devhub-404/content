# Colors, Alpha, and `currentColor`

CSS supports named colors, hex, `rgb()`, `hsl()`, `hwb()`, Lab/LCH, OKLab/OKLCH, and `color()` spaces. Alpha is transparency on a particular color value; the `opacity` property instead composites the entire rendered element subtree with reduced opacity.

```css
.button {
  color: oklch(52% .2 255);
  border: 1px solid currentColor;
  background: rgb(255 255 255 / .9);
}
```

`currentColor` resolves to the element's computed `color`, making it useful for borders, icons, SVG fills, and decorations that should follow text color. Perceptual spaces such as OKLCH are useful for systematic lightness and chroma adjustments. Wide-gamut values can show colors outside sRGB on capable displays, so provide an acceptable fallback when that difference matters.
