# Nesting Nativo do CSS

Nesting nativo permite manter seletores relacionados e regras condicionais dentro de uma regra pai. Um seletor aninhado pode começar com combinador, e `&` representa explicitamente o seletor pai quando necessário para estados ou combinações mais complexas.

```css
.card {
  padding: 1rem;

  > h2 {
    margin-block-start: 0;
  }

  &:hover {
    border-color: #888;
  }

  @media (width >= 40rem) {
    padding: 1.5rem;
  }
}
```

Nesting muda a organização, não a cascata subjacente. O seletor efetivo ainda tem especificidade e pode ficar frágil se você criar cadeias profundas. Mantenha o nesting raso o suficiente para que a relação resultante seja óbvia. Regras `@media` ou `@container` aninhadas podem ser úteis porque mudanças responsivas do componente ficam próximas aos estilos-base.
