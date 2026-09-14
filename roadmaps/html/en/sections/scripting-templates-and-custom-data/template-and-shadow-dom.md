# `template`, Declarative Shadow DOM, and Slots

`template` stores parsed markup that is inert until code uses it. This is useful for repeated DOM structure that should live in HTML rather than in long JavaScript strings. JavaScript can clone the template's `content`, populate it, and insert the result into the document.

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

A template with `shadowrootmode` can declare a Shadow DOM tree directly in HTML. Inside a shadow tree, `slot` elements define insertion points for light-DOM children; named slots match children with a corresponding `slot` attribute. Shadow DOM changes styling, event, and tree relationships, so use it when encapsulation is an intentional component boundary.
