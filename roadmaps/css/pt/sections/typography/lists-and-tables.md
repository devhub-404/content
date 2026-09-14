# Estilizando Listas e Tabelas

A apresentação de listas pode ser controlada com `list-style-*`, `::marker` e counters CSS preservando a semântica de lista do HTML. Use CSS para mudar marcadores ou numeração em vez de substituir listas reais por elementos genéricos apenas para controle visual.

```css
li::marker {
  color: #2457d6;
  font-weight: 700;
}

table {
  border-collapse: collapse;
  inline-size: 100%;
}

th,
td {
  padding: .75rem;
  text-align: start;
}
```

Tabelas possuem formatting model especializado com border spacing/collapse, table layout, sizing de colunas e alinhamento de células. Estilize dados realmente tabulares em vez de usar tabelas para layout de página. Em telas estreitas, um scroll container horizontal local frequentemente preserva relações linha/coluna melhor do que transformar elementos de tabela em caixas block sem relação.
