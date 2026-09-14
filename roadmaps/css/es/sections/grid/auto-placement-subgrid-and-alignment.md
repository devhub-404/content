# Auto-placement, alineación y subgrid

Los items sin posición explícita usan el algoritmo de auto-placement. `grid-auto-flow` define la dirección, mientras `grid-auto-rows` y `grid-auto-columns` dimensionan tracks implícitas. El modo dense puede rellenar huecos, pero también separar el orden visual del source.

```css
.gallery {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-auto-rows: 10rem;
}

.card {
  display: grid;
  grid-template-rows: subgrid;
  grid-row: span 3;
}
```

Grid usa las propiedades de Box Alignment. `subgrid` permite que un grid anidado reutilice el sizing de tracks de su padre y resulta útil para alinear partes de varias tarjetas. Usa un grid independiente cuando el hijo deba controlar su geometría; usa subgrid cuando la relación real sea compartir tracks.
