# `:is()`, `:where()`, `:not()` y `:has()`

`:is()` agrupa alternativas y toma la especificidad de su argumento más específico. `:where()` coincide de forma parecida pero aporta especificidad cero. `:not()` excluye coincidencias y `:has()` permite seleccionar un elemento según relaciones con descendientes o hermanos.

```css
article :is(h2, h3, h4) { line-height: 1.2; }
:where(article, section) > p { max-inline-size: 68ch; }
button:not(:disabled) { cursor: pointer; }
.card:has(img) { grid-template-columns: 8rem 1fr; }
```

Elige `:is()` o `:where()` según la intención de cascada, no solo para ahorrar texto. `:has()` es excelente cuando la relación ya existe en el DOM, como cambiar un card si contiene una imagen. Estado de aplicación conocido por JavaScript a veces sigue siendo más claro como clase o `data-*` explícito.
