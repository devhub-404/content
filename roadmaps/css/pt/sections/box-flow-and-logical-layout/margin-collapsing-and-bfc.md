# Colapso de Margens e Block Formatting Contexts

Margens adjacentes no eixo de bloco em fluxo normal podem colapsar em vez de se somarem. Margens de pai e primeiro/último filho também podem colapsar em condições específicas. Margens de itens flex e grid não colapsam. Por isso, dois parágrafos com `margin-block: 1rem` não necessariamente têm espaço de 2rem entre si.

```css
.stack > * + * {
  margin-block-start: 1rem;
}

.isolated {
  display: flow-root;
}
```

Um block formatting context isola várias interações do fluxo de blocos, incluindo contenção de floats e algumas relações de margem. `display: flow-root` é a forma direta de criar um sem mudar para flex ou grid. Para ritmo vertical previsível, padrões de espaçamento em uma direção, como adicionar margem apenas entre filhos adjacentes, são mais fáceis de raciocinar do que margens simétricas em todo lugar.
