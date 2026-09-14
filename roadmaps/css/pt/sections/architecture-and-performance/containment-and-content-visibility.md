# Containment e `content-visibility`

Containment informa ao navegador que uma subárvore pode ser tratada como independente em aspectos como size, inline-size, layout, style ou paint. Isso pode reduzir o escopo de trabalho de layout e pintura, mas containment também muda comportamento como containing blocks, stacking, clipping e sizing intrínseco.

```css
.widget {
  contain: layout paint;
}

.feed-item {
  content-visibility: auto;
  contain-intrinsic-size: auto 24rem;
}
```

`content-visibility: auto` permite ao navegador pular grande parte do rendering de conteúdo fora da tela mantendo-o no documento. Uma estimativa de intrinsic size pode reduzir saltos de scroll antes de o conteúdo ser renderizado. Use esses recursos em regiões grandes e independentes após testar consequências de layout; containment não é um botão gratuito de performance.
