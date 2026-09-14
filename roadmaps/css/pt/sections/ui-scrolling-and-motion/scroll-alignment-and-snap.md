# Alinhamento de Scroll, Snap, Overscroll e Scrollbars

`scroll-padding` reserva um inset ideal de visualização dentro de um scroll container, enquanto `scroll-margin` expande a área de alinhamento do alvo. São úteis para fragment links e alvos de foco que ficariam sob UI sticky. Scroll snap define posições preferidas de repouso com `scroll-snap-type` no container e `scroll-snap-align` nos itens.

```css
html {
  scroll-padding-block-start: 5rem;
}

.carousel {
  display: flex;
  overflow-x: auto;
  scroll-snap-type: inline mandatory;
  overscroll-behavior-inline: contain;
}

.carousel > * {
  scroll-snap-align: start;
}
```

`overscroll-behavior` controla scroll chaining nas bordas. Estilo de scrollbar oferece controle limitado de largura/cor, mas deve preservar descoberta e preferências do sistema. Evite snapping mandatory em superfícies longas de leitura e não esconda scrollbars apenas por limpeza visual. Regiões roláveis precisam funcionar com mouse, touch, teclado e navegação assistiva.
