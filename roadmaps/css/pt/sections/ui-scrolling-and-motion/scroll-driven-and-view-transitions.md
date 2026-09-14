# Animações por Scroll e View Transitions

Scroll-driven animations usam progresso de scroll ou view como timeline em vez de tempo decorrido. Isso é útil para indicadores de progresso e efeitos que realmente correspondem à rolagem. O mesmo modelo de keyframes é usado; apenas a fonte da timeline muda.

```css
.reading-progress {
  transform-origin: left;
  animation: grow linear both;
  animation-timeline: scroll(root block);
}

@keyframes grow {
  from { scale: 0 1; }
  to   { scale: 1 1; }
}

.product-card {
  view-transition-name: selected-product;
}
```

View transitions animam continuidade visual entre estados antigo e novo expondo pseudo-elementos de snapshot gerenciados pelo navegador. Elementos nomeados podem ser conectados entre estados. Os dois sistemas são progressive enhancements: conteúdo, navegação e mudança de estado precisam continuar corretos sem animação, e preferências de movimento reduzido devem ser respeitadas.
