# Ordem do Código e Ordem de Foco

Escreva o HTML na ordem em que um leitor deve encontrar o conteúdo. CSS Grid e Flexbox podem mudar a posição visual, mas normalmente não alteram a ordem de leitura do DOM nem a sequência de foco pelo teclado. Um rearranjo visualmente bonito pode criar uma página cuja sequência de teclado ou leitor de tela parece desconectada do que aparece na tela.

```html
<main>
  <h1>Checkout</h1>

  <section>
    <h2>Contact details</h2>
    ...
  </section>

  <section>
    <h2>Payment</h2>
    ...
  </section>
</main>
```

Use o DOM como ordem canônica de conteúdo e interação e deixe o CSS criar colunas, sidebars e arranjos responsivos que preservem essa lógica. Evite tabindex positivo como correção para ordem ruim do código. Se o design exige uma sequência radicalmente diferente, reconsidere a marcação ou o próprio design em vez de manter duas ordens concorrentes.
