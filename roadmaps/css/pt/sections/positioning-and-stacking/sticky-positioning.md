# Posicionamento Sticky

Uma caixa sticky permanece no fluxo normal até que a rolagem a leve além de um limite de inset especificado; então fica restringida ao scrollport. Ela precisa de um inset relevante como `inset-block-start`; sem limite não há contra o que “grudar”.

```css
.section-title {
  position: sticky;
  inset-block-start: 0;
  background: Canvas;
  z-index: 1;
}
```

Overflow dos ancestrais importa porque um ancestral rolável pode virar o scroll container relevante. Cabeçalhos sticky também precisam de background e stacking deliberados para que o conteúdo por baixo não fique ilegível. Como o elemento ainda ocupa seu espaço no fluxo normal, sticky costuma integrar melhor que um header fixed quando o objetivo é persistência local durante a rolagem.
