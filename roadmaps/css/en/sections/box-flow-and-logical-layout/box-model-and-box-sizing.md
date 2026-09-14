# The Box Model and `box-sizing`

A CSS box has content, padding, border, and margin areas. With the default `content-box`, a declared width or height describes the content box, so padding and borders add to the outer size. `border-box` makes the declared size include padding and border and is a common baseline because component sizing becomes easier to predict.

```css
*,
*::before,
*::after {
  box-sizing: border-box;
}

.card {
  inline-size: 20rem;
  padding: 1rem;
  border: 1px solid #ccc;
  margin-block: 1rem;
}
```

Padding creates space inside the border; margin creates space outside it. Backgrounds paint through specific box areas while margins remain transparent. Use DevTools' box-model view when sizing is surprising. Many “why is this wider than 300px?” problems are simply confusion about which box edge a value describes.
