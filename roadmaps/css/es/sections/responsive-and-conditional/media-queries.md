# Media queries y sintaxis de rangos

`@media` aplica reglas según características como tamaño del viewport, orientación, resolución, capacidad de color o preferencias del usuario. La sintaxis moderna de comparación permite expresar rangos de forma directa y legible.

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

Mantén fuera de la query un baseline simple y robusto y mejora cuando otra disposición aporte valor. No crees breakpoints para cada pequeña diferencia. Si la condición depende del tamaño de un componente reutilizable en vez del viewport, una container query suele expresar mejor la relación.
