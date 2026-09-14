# `will-change` y rendimiento de rendering

Un cambio de CSS puede provocar recálculo de estilos, layout, paint y compositing según la propiedad y el contexto. Transform y opacity a menudo evitan layout repetido, pero el coste depende del tamaño de la superficie, efectos, dispositivo y navegador.

```css
.dragging {
  will-change: transform;
}

/* Remove the hint when the interaction ends. */
```

`will-change` es una pista de que algo cambiará pronto y puede hacer que el navegador reserve recursos. Usarlo en exceso consume memoria y puede empeorar rendimiento. Aplícalo justo antes de una interacción costosa cuando las mediciones lo justifiquen y retíralo después.
