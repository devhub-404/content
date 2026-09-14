# Alinhamento Flex, Gaps e Margens Auto

`justify-content` distribui itens ou espaço livre no eixo principal. `align-items` alinha itens no eixo transversal, e `align-self` sobrescreve um item. `gap` cria espaçamento consistente entre itens sem margens externas indesejadas. `align-content` se aplica a múltiplas linhas flex, não ao alinhamento comum dentro de uma linha.

```css
.nav {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.nav__account {
  margin-inline-start: auto;
}
```

Margens auto absorvem espaço livre e são úteis para empurrar um item ou grupo para longe dos irmãos. No exemplo, o item da conta vai ao fim inline sem depender de `space-between`. Como os eixos seguem `flex-direction`, confira a direção antes de concluir que uma propriedade de alinhamento está agindo “ao contrário”.
