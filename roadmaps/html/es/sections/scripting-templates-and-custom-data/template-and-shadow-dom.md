# `template`, Shadow DOM declarativo y slots

`template` almacena marcado ya parseado que permanece inerte hasta que el código lo utiliza. Es útil para estructuras DOM repetidas que deben vivir en HTML en lugar de largas cadenas JavaScript. El script puede clonar `content`, rellenarlo e insertar la copia en el documento.

```html
<template id="task-template">
  <li class="task">
    <span class="task__name"></span>
  </li>
</template>

<article>
  <template shadowrootmode="open">
    <header><slot name="title"></slot></header>
    <slot></slot>
  </template>

  <h2 slot="title">Card title</h2>
  <p>Card body</p>
</article>
```

Un template con `shadowrootmode` puede declarar una Shadow DOM directamente en HTML. Dentro de esa sombra, los elementos `slot` definen puntos de inserción para hijos del light DOM, y los slots con nombre reciben hijos con el atributo `slot` correspondiente. Usa Shadow DOM cuando el encapsulamiento sea una frontera intencional del componente.
