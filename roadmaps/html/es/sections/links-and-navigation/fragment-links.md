# Enlaces de fragmento e IDs

Un fragmento de URL que empieza por `#` apunta al elemento cuyo `id` coincide con ese fragmento. Así funcionan índices, skip links, deep links y navegación a una región concreta del documento. Los IDs usados como destinos deben ser únicos dentro de la página.

```html
<a href="#shipping">Jump to shipping</a>

<section id="shipping">
  <h2>Shipping</h2>
  <p>Orders leave within two business days.</p>
</section>
```

El fragmento forma parte de la URL, por lo que el usuario puede guardar o compartir esa ubicación. Mantén IDs estables si pueden existir enlaces externos. CSS puede usar `scroll-margin` para impedir que un destino quede oculto bajo una cabecera sticky, pero la relación entre enlace y destino pertenece al HTML.
