# `hidden` e `inert`

`hidden` indica que un elemento no es relevante actualmente para la presentación y deja de renderizarse de la manera normal. `inert` es distinto: hace que una subárbol no sea interactivo y la retira de la interacción normal de foco y accesibilidad, aunque pueda seguir visible.

```html
<section hidden>
  <h2>Draft report</h2>
</section>

<main inert>
  ...
</main>
```

Usa cada atributo para el estado que representa. Contenido que no forma parte de la interfaz actual puede ocultarse; contenido temporalmente no disponible porque otra interacción requiere atención puede volverse inert. Los diálogos modales nativos ya gestionan la inercia del fondo, así que no añadas mecanismos superpuestos sin una razón concreta.
