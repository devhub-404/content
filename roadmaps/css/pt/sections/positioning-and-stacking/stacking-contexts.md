# Stacking Contexts e `z-index`

`z-index` não cria uma única linha numérica global da página. Elementos são agrupados em stacking contexts, e filhos são ordenados dentro do próprio contexto. Um filho com `z-index: 9999` não consegue escapar de um contexto ancestral pintado abaixo de um contexto irmão.

```css
:root {
  --z-sticky: 10;
  --z-overlay: 100;
  --z-modal: 110;
}

.site-header {
  position: sticky;
  z-index: var(--z-sticky);
}
```

Elementos posicionados com `z-index` não-auto, transforms, opacidade abaixo de 1, filters, isolation e alguns recursos de containment podem criar stacking contexts. Quando a sobreposição está errada, inspecione as fronteiras do contexto em vez de aumentar números indefinidamente. Uma escala pequena e documentada para sticky UI, overlays, modais e toasts é mais fácil de manter que valores arbitrários.
