# Containment y `content-visibility`

Containment permite indicar que una subárbol puede tratarse como independiente en aspectos como size, layout, style o paint. Puede reducir el trabajo del navegador, pero también cambia containing blocks, stacking, clipping y sizing intrínseco.

```css
.widget {
  contain: layout paint;
}

.feed-item {
  content-visibility: auto;
  contain-intrinsic-size: auto 24rem;
}
```

`content-visibility: auto` permite omitir gran parte del rendering de contenido fuera de pantalla manteniéndolo en el documento. `contain-intrinsic-size` ayuda a reservar espacio. Usa estas técnicas en regiones grandes e independientes después de comprobar sus consecuencias; no son un interruptor de rendimiento gratis.
