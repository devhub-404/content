# Controles de formulario, foco y accent color

Los controles nativos tienen estilos del navegador y sistema. Empieza heredando tipografía y cambiando espaciado, bordes, colores y `accent-color` antes de eliminar la apariencia nativa. `appearance: none` transfiere más responsabilidad a tu CSS.

```css
input,
button,
select,
textarea {
  font: inherit;
}

input[type="checkbox"],
input[type="radio"] {
  accent-color: #2457d6;
}

:focus-visible {
  outline: 3px solid Highlight;
  outline-offset: 3px;
}
```

El foco visible es esencial para teclado. `:focus-visible` permite una señal clara cuando corresponde. Mantén targets táctiles suficientes, deja que labels y errores hagan wrap y prueba zoom, forced colors, teclado y touch. Estilizar debe mejorar el control nativo, no ocultarlo y reconstruirlo peor.
