# `template`, Shadow DOM Declarativo e Slots

`template` armazena marcação já analisada que fica inerte até ser usada pelo código. Isso é útil para estruturas DOM repetidas que devem viver em HTML em vez de longas strings JavaScript. O script pode clonar o `content` do template, preencher valores e inserir o resultado no documento.

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

Um template com `shadowrootmode` pode declarar uma árvore Shadow DOM diretamente em HTML. Dentro dela, elementos `slot` definem pontos de inserção para filhos do light DOM; slots nomeados correspondem a filhos com o atributo `slot` adequado. Shadow DOM altera relações de estilo, eventos e árvore, então use quando encapsulamento for uma fronteira intencional de componente.
