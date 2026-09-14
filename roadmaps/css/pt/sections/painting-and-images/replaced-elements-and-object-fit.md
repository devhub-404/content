# Elementos Substituídos e Object Fitting

Imagens, vídeo e alguns controles são replaced elements: o conteúdo externo possui dimensões intrínsecas que participam do sizing. `aspect-ratio` fornece uma proporção preferida quando uma dimensão é automática, ajudando mídia responsiva a reservar geometria previsível.

```css
.thumbnail {
  inline-size: 100%;
  aspect-ratio: 16 / 9;
  object-fit: cover;
  object-position: 50% 35%;
}
```

`object-fit` controla como o conteúdo substituído cabe em sua content box. `cover` preenche e corta excesso; `contain` preserva o objeto inteiro com possível letterboxing; `fill` pode distorcer. `object-position` escolhe o alinhamento focal. Não force width e height sem relação que estiquem o conteúdo; escolha estratégia que preserve a geometria pretendida.
