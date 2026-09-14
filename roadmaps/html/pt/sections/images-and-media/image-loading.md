# Carregamento e Prioridade de Imagens

`loading="lazy"` permite ao navegador adiar o download de uma imagem fora da tela até que ela esteja mais próxima de ser necessária. É útil em páginas longas e galerias, mas normalmente é uma escolha ruim para a imagem principal visível imediatamente, pois atrasá-la pode prejudicar a percepção e as métricas de carregamento.

```html
<img
  src="gallery-12.jpg"
  alt="Ceramic bowl with blue glaze"
  width="800"
  height="600"
  loading="lazy">

<img
  src="hero.jpg"
  alt="Team working in the studio"
  fetchpriority="high">
```

`fetchpriority` é uma dica sobre prioridade relativa de requisição. Use com parcimônia para recursos identificados como especialmente importantes ou pouco importantes; o agendamento do navegador já considera muitos fatores. Atributos de carregamento são dicas de desempenho, não semântica. Eles não substituem alt correto, dimensões, fontes responsivas ou otimização da imagem.
