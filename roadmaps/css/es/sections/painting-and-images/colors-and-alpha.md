# Colores, alpha y `currentColor`

CSS admite múltiples sintaxis de color: nombres, hex, `rgb()`, `hsl()`, Lab/LCH, OKLab/OKLCH y espacios `color()`. Alpha aplica transparencia a un color concreto; `opacity` compone todo el subárbol renderizado con una opacidad menor.

```css
.button {
  color: oklch(52% .2 255);
  border: 1px solid currentColor;
  background: rgb(255 255 255 / .9);
}
```

`currentColor` toma el `color` computado del elemento y es útil para bordes, iconos y decoraciones que deben seguir el texto. Espacios perceptuales como OKLCH facilitan sistemas de color consistentes. Cuando uses wide gamut, conserva un fallback aceptable para pantallas que no lo representan.
