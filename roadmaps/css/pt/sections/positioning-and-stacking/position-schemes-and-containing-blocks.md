# Esquemas de Posição e Containing Blocks

`position: static` mantém o comportamento normal. `relative` mantém a caixa no fluxo, mas permite offsets visuais e normalmente estabelece containing block para descendentes posicionados. `absolute` remove a caixa do fluxo normal e a posiciona usando um containing block. `fixed` geralmente é relativo ao viewport, enquanto `sticky` combina participação no fluxo com restrições de rolagem.

```css
.card {
  position: relative;
}

.card__badge {
  position: absolute;
  inset-block-start: .5rem;
  inset-inline-end: .5rem;
}
```

Offsets como `inset`, `top` ou insets lógicos só fazem sentido depois que você sabe qual é o containing block. Ancestrais posicionados frequentemente o estabelecem, mas transforms, containment e outros recursos também podem afetar a caixa de referência. Quando um elemento absolute ou fixed aparece no lugar errado, identifique o containing block antes de mudar números.
