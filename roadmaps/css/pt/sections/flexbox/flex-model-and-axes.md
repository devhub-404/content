# Flex Containers, Itens e Eixos

`display: flex` ou `inline-flex` transforma filhos diretos em flex items. Flexbox é unidimensional: organiza itens ao longo de um eixo principal e os alinha em um eixo transversal. `flex-direction` escolhe o eixo principal, com valores `row`, `row-reverse`, `column` e `column-reverse` que seguem writing mode e direction.

```css
.toolbar {
  display: flex;
  align-items: center;
  gap: .75rem;
}
```

Pense em eixos main/cross em vez de fixar “horizontal” e “vertical”. Flexbox é ótimo para toolbars, navegação, grupos de botões, media objects e outros layouts onde uma dimensão é a relação principal. Apenas filhos diretos viram flex items; descendentes mais profundos mantêm seu formatting context até outra regra alterá-lo.
