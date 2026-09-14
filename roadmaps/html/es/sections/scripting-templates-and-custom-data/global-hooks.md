# `id`, `class` y `data-*`

`id` identifica un elemento dentro del documento y debe ser único cuando funciona como identificador. Se usa en navegación por fragmentos, relaciones label/control, relaciones ARIA, scripts y estilos. `class` proporciona uno o más nombres reutilizables y es el gancho habitual para componentes y utilidades CSS.

```html
<section id="pricing" class="panel featured">
  <button data-product-id="sku-4182">Add to cart</button>
</section>
```

Los atributos `data-*` almacenan datos específicos de la aplicación y JavaScript puede leerlos mediante `dataset`. Úsalos para datos que realmente pertenecen a tu aplicación, no para reinventar atributos estándar. IDs, clases y data attributes son ganchos técnicos; por sí mismos no aportan significado semántico al contenido.
