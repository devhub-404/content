# `typeof`, `auto` e Inferência de Tipo no C23

C23 adiciona recursos padronizados de inferência e consulta de tipo, incluindo `auto` em declarações inferidas e `typeof`/`typeof_unqual`. Eles reduzem repetição quando o tipo já é determinado pelo initializer ou expressão.

```c
auto x = 42;
typeof(x) y = 7;
typeof_unqual(x) z = 9;
```

Isso não torna C dinâmico: o compilador ainda determina um tipo estático na tradução. Use inferência quando remover duplicação frágil sem esconder um tipo importante de interface e observe qualifiers e conversions da expressão consultada.
