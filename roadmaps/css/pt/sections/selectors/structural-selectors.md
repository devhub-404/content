# Pseudo-classes Estruturais

Pseudo-classes estruturais correspondem a elementos pela estrutura entre irmãos. `:first-child`, `:last-child`, `:only-child`, variantes por tipo e a família `:nth-*()` cobrem relações posicionais comuns. `:nth-child()` aceita fórmulas como `odd`, `2n` ou `3n + 1`, e a sintaxe moderna pode contar apenas irmãos que correspondam a um seletor em `of`.

```css
li:first-child { margin-block-start: 0; }
tr:nth-child(even) { background: rgb(0 0 0 / .04); }
.card:nth-child(-n + 3 of .featured) { border-width: 2px; }
```

Use seletores estruturais quando posição realmente faz parte da apresentação, como linhas alternadas de tabela ou espaçamento entre irmãos. Não codifique estado de negócio pela posição: se um item é featured independentemente de onde aparece, mantenha esse estado explícito no markup e use o seletor estrutural apenas para a parte posicional.
