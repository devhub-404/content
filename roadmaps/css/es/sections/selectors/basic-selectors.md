# Selectores de tipo, clase, ID y universal

Un selector de tipo coincide con nombres de elementos, una clase con tokens de `class`, un selector de ID con `id` y `*` con cualquier elemento sin añadir especificidad. Las clases suelen ser el gancho reutilizable más práctico porque pueden compartirse sin el peso de los IDs.

```css
p { color: #333; }
.note { background: #fff8c5; }
#main-title { letter-spacing: -.02em; }
* { box-sizing: border-box; }
```

Una lista separada por comas permite compartir declaraciones entre varios selectores. Evita rutas DOM largas y frágiles. Un ID es CSS válido, pero usarlo como gancho de estilo rutinario hace que futuras sobrescrituras sean más difíciles de lo necesario.
