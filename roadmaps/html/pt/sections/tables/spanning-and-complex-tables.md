# Células Mescladas e Tabelas Complexas

`rowspan` e `colspan` permitem que uma célula ocupe várias posições de linha ou coluna. São úteis para cabeçalhos hierárquicos, totais e dados agrupados, mas também tornam o grafo de relações mais complexo. Prefira a estrutura mais simples que represente os dados com precisão.

```html
<table>
  <tr>
    <th rowspan="2">Region</th>
    <th colspan="2">Revenue</th>
  </tr>
  <tr>
    <th>Q1</th>
    <th>Q2</th>
  </tr>
  <tr>
    <th>North</th>
    <td>$42k</td>
    <td>$48k</td>
  </tr>
</table>
```

Para tabelas complexas, teste como o contexto de cabeçalho é anunciado por tecnologias assistivas. Associações explícitas com `id` e `headers` existem quando escopos simples de linha e coluna não bastam. O design responsivo deve preservar as relações dos dados: rolagem horizontal costuma ser mais segura do que transformar cada linha em blocos sem contexto de coluna.
