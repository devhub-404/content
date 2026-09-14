# Compatibilidade, Entrega Progressiva e Depuração

CSS é um conjunto de módulos com diferentes níveis de maturidade de especificação e adoção pelos navegadores. Um recurso aparecer em uma spec não significa que todos os navegadores-alvo suportam a mesma sintaxe ou subfeature. Verifique compatibilidade da feature exata e decida se ela é obrigatória, enhancement ou opcional para seu produto.

```css
.component {
  display: block;
}

@supports (display: grid) {
  .component {
    display: grid;
  }
}
```

Construa baseline robusto, adicione melhorias e teste os dois caminhos. No DevTools, depure em etapas: match do seletor, vencedor da cascata, valor computado, containing block, algoritmo de layout, overflow, stacking context e então pintura/compositing. Adicionar widths, `position`, `z-index` enorme ou `!important` aleatoriamente pode esconder o sintoma mantendo o modelo errado.
