# Números, dimensiones y porcentajes

Los valores CSS tienen tipos definidos por el contexto: números sin unidad, longitudes, ángulos, tiempos, porcentajes, colores, imágenes y otros. `16px` no es intercambiable con un ángulo o un tiempo, y el mismo número puede tener significados distintos según la propiedad.

```css
.box {
  inline-size: 20rem;
  rotate: 5deg;
  transition-duration: 200ms;
  opacity: .8;
  max-inline-size: 80%;
}
```

Los porcentajes son relativos, pero la referencia depende de la propiedad. `width: 50%` no implica que todo porcentaje se mida «contra el padre». Consulta qué define cada propiedad. El cero suele poder escribirse sin unidad de longitud, aunque otros tipos como tiempo o ángulo pueden exigir una unidad.
