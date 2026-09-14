# Atributos, clases y data attributes

Los elementos DOM exponen propiedades JavaScript y atributos HTML. Muchas propiedades reflejan atributos, pero las reglas exactas varían. Usa propiedades de estado live como `input.value` o `button.disabled` cuando correspondan y métodos de atributo para trabajar con la representación serializada.

```js
button.disabled = true;
button.classList.toggle("is-active", active);
button.dataset.userId = String(user.id);

const label = button.getAttribute("aria-label");
```

`classList` añade, elimina y alterna clases, mientras `dataset` mapea `data-*` a strings. Los atributos booleanos HTML funcionan por presencia: establecer el texto `"false"` no los desactiva. Entiende primero la semántica del atributo antes de elegir cómo modificarlo.
