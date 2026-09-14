# `display` e Fluxo Normal

O fluxo normal organiza um documento útil antes de você escolher um sistema de layout especializado. Caixas block geralmente empilham na direção de bloco e usam o espaço inline disponível; conteúdo inline participa de line boxes com o texto ao redor. A propriedade `display` controla a participação externa e o formatting context interno.

```css
.badge { display: inline-block; }
.toolbar { display: flex; }
.gallery { display: grid; }
.wrapper { display: flow-root; }
```

`inline-block` é uma caixa atômica de nível inline com sizing interno semelhante a bloco. `flex` e `grid` criam seus respectivos formatting contexts para filhos diretos. `flow-root` cria um block formatting context independente. `display: none` remove uma subárvore da geração de caixas, enquanto `display: contents` remove a caixa principal do elemento mas mantém as caixas descendentes; use `contents` com cuidado porque remover a caixa pode afetar acessibilidade e outros comportamentos.
