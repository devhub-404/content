# Layout responsivo antes de breakpoints

CSS responsivo empieza con flujo flexible y restricciones, no con una lista de dispositivos. Deja que bloques usen espacio disponible, imágenes respeten el contenedor, texto haga wrap, Flexbox envuelva y Grid cree tracks intrínsecas antes de añadir media queries.

```css
.page {
  inline-size: min(72rem, calc(100% - 2rem));
  margin-inline: auto;
}

img {
  max-inline-size: 100%;
  block-size: auto;
}
```

Añade un breakpoint cuando el diseño realmente necesite un cambio discreto, como pasar de una a dos columnas. Elige el umbral a partir del contenido, no del nombre de un teléfono. Responsive también incluye zoom, fuentes de usuario, orientación, métodos de entrada y textos traducidos más largos.
