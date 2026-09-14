# Restricciones de tamaño y tamaños intrínsecos

`width`/`height` y sus formas lógicas expresan tamaños preferidos; `min-*` y `max-*` añaden límites. Los contenedores de texto suelen necesitar altura automática para crecer con contenido, zoom, traducciones y preferencias del usuario.

```css
.article {
  inline-size: 100%;
  max-inline-size: 70rem;
}

.label {
  inline-size: fit-content;
}

.grid {
  grid-template-columns: minmax(0, 1fr) max-content;
}
```

`min-content`, `max-content` y `fit-content` representan tamaños que dependen del contenido. Flexbox y Grid usan esas contribuciones intensamente. Un minimum automático explica muchos casos en que un item no quiere encogerse hasta que aparece `min-inline-size: 0` o `minmax(0, 1fr)`.
