# Placement, Spans e Áreas no Grid

Grid placement é baseado em linhas. Itens podem ser posicionados com linhas numeradas, linhas nomeadas, `span` ou áreas nomeadas. Números negativos contam do fim do grid explícito, tornando `1 / -1` um padrão útil para ocupar tudo. Template areas tornam layouts de regiões legíveis desde que cada área nomeada forme um retângulo.

```css
.page {
  display: grid;
  grid-template:
    "header header" auto
    "sidebar main" 1fr
    / 16rem 1fr;
}

header { grid-area: header; }
aside  { grid-area: sidebar; }
main   { grid-area: main; }

.wide { grid-column: 1 / -1; }
```

Placement explícito muda posição visual, não ordem no código. Mantenha o DOM em sequência significativa de leitura e foco mesmo se o grid colocar regiões em outro lugar visualmente. Use placement quando a geometria é realmente o requisito; não reorganize ordem semântica apenas porque Grid facilita.
