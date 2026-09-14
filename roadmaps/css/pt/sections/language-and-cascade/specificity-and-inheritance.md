# Especificidade e Herança

Especificidade compara seletores depois que critérios mais fortes da cascata empataram. IDs contribuem mais que classes, atributos e pseudo-classes; esses contribuem mais que seletores de tipo e pseudo-elementos. Combinadores não adicionam especificidade. `:where()` é especial porque sempre contribui zero.

```css
p { color: black; }
.note { color: navy; }
#warning { color: crimson; }

article {
  color: #333;
  font-family: system-ui;
}
```

Herança é um mecanismo separado. Algumas propriedades, especialmente de texto como `color` e várias propriedades de fonte, normalmente herdam do pai; propriedades de caixa e layout geralmente não. `inherit` recebe explicitamente o valor computado do pai, enquanto `initial`, `unset`, `revert` e `revert-layer` escolhem outros pontos de fallback. Mantenha seletores baixos o suficiente para que overrides normais não exijam escalada de especificidade.
