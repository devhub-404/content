# Estrutura da Tabela e Cabeçalhos

Use tabelas para dados cujo significado depende de linhas e colunas. `table` contém linhas (`tr`), e linhas contêm células de dados (`td`) ou cabeçalhos (`th`). `caption` dá um nome à tabela. `thead`, `tbody` e `tfoot` podem agrupar linhas em regiões lógicas quando essa estrutura é útil.

```html
<table>
  <caption>Orders by month</caption>
  <thead>
    <tr>
      <th scope="col">Month</th>
      <th scope="col">Orders</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">January</th>
      <td>120</td>
    </tr>
  </tbody>
</table>
```

Células `th` devem representar rótulos reais de linha ou coluna. `scope="col"` e `scope="row"` tornam relações simples explícitas e ajudam tecnologias assistivas a fornecer contexto enquanto o usuário navega pelas células. Não crie uma tabela visual com caixas genéricas quando os dados são tabulares, e não use uma tabela HTML apenas para fazer layout de página.
