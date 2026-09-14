# Layers, Scope e `!important`

Cascade layers criam grupos explícitos de precedência dentro de uma origem. Para declarações normais de autor, layers posteriores vencem anteriores independentemente da especificidade do seletor. Declarações importantes invertem a prioridade de layers. Isso torna layers uma ferramenta de arquitetura melhor do que aumentar peso de seletor até uma regra vencer.

```css
@layer reset, base, components, utilities;

@layer components {
  .button { padding: .6rem 1rem; }
}

@layer utilities {
  .p-0 { padding: 0; }
}

@scope (.article) {
  a { color: #2457d6; }
}
```

`@scope` limita regras a uma região do DOM e adiciona proximidade de escopo como desempate tardio da cascata. `!important` muda a precedência de origem/layer; não é “especificidade máxima”. Reserve-o para contratos deliberados, porque uso rotineiro dificulta overrides e pode atrapalhar personalização do usuário. CSS normal não-layered de autor vence CSS normal em layers, então misture os dois de propósito.
