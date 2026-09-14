# `article`, `section` e `aside`

`article` representa uma composição autocontida, como post, notícia, entrada de fórum, comentário ou outro item que faça sentido de forma independente. `section` representa um agrupamento temático dentro de um documento, normalmente identificado por um título. Um wrapper genérico de estilização não vira automaticamente uma section.

```html
<article>
  <h2>Release 4.2 is available</h2>

  <section>
    <h3>Highlights</h3>
    <p>...</p>
  </section>

  <aside>
    <h3>Related links</h3>
    ...
  </aside>
</article>
```

`aside` representa conteúdo relacionado ao conteúdo ao redor, mas que não faz parte do fluxo principal, como notas contextuais, recursos relacionados ou barra lateral complementar. Esses elementos descrevem relações no conteúdo, não geometria de tela. Um aside não precisa aparecer de lado e um article não precisa parecer uma notícia de jornal.
