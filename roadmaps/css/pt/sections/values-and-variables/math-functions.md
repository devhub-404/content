# Funções Matemáticas do CSS

`calc()` combina expressões numéricas compatíveis, inclusive valores com unidades diferentes. `min()` escolhe o menor candidato, `max()` o maior e `clamp(min, preferred, max)` limita um valor preferido. Essas funções permitem expressar restrições diretamente em vez de simular cada tamanho intermediário com breakpoints.

```css
main {
  inline-size: min(70rem, calc(100% - 2rem));
  margin-inline: auto;
}

h1 {
  font-size: clamp(2rem, 5vw, 4rem);
}
```

Sizing fluido é útil quando a relação é contínua, como espaçamento ou tipografia que deve crescer dentro de limites razoáveis. Ele não substitui regras condicionais para mudanças de modo de layout. Se uma sidebar deve ir para baixo do conteúdo principal, essa é uma decisão discreta de layout e pertence a media ou container query, não a um `calc()` cada vez mais complexo.
