# Aninhamento e Parsing do Navegador

Elementos HTML podem ser aninhados, mas nem todo elemento é permitido dentro de qualquer outro. Feche elementos aninhados na ordem inversa em que foram abertos e respeite o modelo de conteúdo de cada elemento. Um aninhamento correto deixa a árvore pretendida clara tanto para pessoas quanto para ferramentas.

```html
<p>
  Read the <strong>important note</strong> first.
</p>
```

O parsing de HTML é propositalmente tolerante a erros. Quando a marcação é inválida, o navegador frequentemente a corrige e ainda constrói um DOM. Isso significa que o DOM pode ser diferente do código-fonte que você imaginou, especialmente com parágrafos, tabelas, formulários e conteúdo interativo. Não dependa dessa recuperação como estilo de programação. Quando a estrutura se comportar de forma inesperada, inspecione o DOM no DevTools e valide a marcação.
