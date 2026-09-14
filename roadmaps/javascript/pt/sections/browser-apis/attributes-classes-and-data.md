# Atributos, Classes e Data Attributes

Elementos DOM expõem propriedades JavaScript e atributos HTML. Muitas propriedades refletem atributos, mas regras exatas variam. Use a propriedade destinada ao estado live quando existir, como `input.value` ou `button.disabled`, e métodos de atributo quando precisar do valor literal serializado.

```js
button.disabled = true;
button.classList.toggle("is-active", active);
button.dataset.userId = String(user.id);

const label = button.getAttribute("aria-label");
```

`classList` adiciona, remove, alterna e testa classes sem analisar string de classes. `dataset` mapeia atributos `data-*` para strings. Atributos booleanos HTML são representados pela presença; definir o atributo como texto `"false"` ainda o deixa presente. Entenda a semântica do recurso HTML antes de escolher método de manipulação DOM.
