# Custom Properties e `var()`

Custom properties armazenam sequências de tokens na cascata e são lidas com `var()`. Elas normalmente herdam, então um valor pode mudar na raiz, fronteira de tema, componente, estado, media query ou container query e descendentes resolverão o valor em cascata mais próximo.

```css
:root {
  --surface: white;
  --text: #161616;
  --space-card: 1rem;
}

.card {
  color: var(--text);
  background: var(--surface);
  padding: var(--space-card, 1rem);
}

[data-theme="dark"] {
  --surface: #161616;
  --text: white;
}
```

O segundo argumento de `var()` é fallback quando a custom property referenciada está ausente ou inválida como valor de custom property; não é fallback de suporte do navegador. Custom properties são substituídas tarde, então uma variável pode existir e ainda tornar a declaração consumidora inválida. Prefira nomes semânticos como `--surface` ou `--space-card` a nomes presos a um literal quando a variável representa um papel de design.
