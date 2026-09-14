# `div`, `span` y agrupación genérica

`div` y `span` son contenedores genéricos sin significado especial. `div` agrupa contenido de flujo y `span` agrupa fragmentos dentro de contenido textual. Son útiles cuando necesitas un gancho para CSS o JavaScript y ningún elemento semántico más específico describe la relación.

```html
<div class="price">
  <span class="amount">$29</span>
  <span class="currency">USD</span>
</div>
```

Los contenedores genéricos no son malos por sí mismos; lo problemático es usarlos sin necesidad. Antes de añadir un `div`, pregunta si el contenido es realmente una sección, artículo, navegación, lista, figura, formulario u otra estructura nativa. Usa el elemento semántico cuando encaje y `div` o `span` cuando el agrupamiento sea puramente técnico o presentacional.
