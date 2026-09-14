# Container Queries e Unidades de Container

Container queries permitem que descendentes respondam a um container ancestral em vez do viewport. `container-type: inline-size` é a escolha comum para layout de componente que depende da largura inline disponível; nomes desambiguam qual container um componente aninhado deve consultar.

```css
.card-shell {
  container: card / inline-size;
}

@container card (width >= 32rem) {
  .card {
    display: grid;
    grid-template-columns: 10rem 1fr;
  }
}

.card h2 {
  font-size: clamp(1.2rem, 5cqi, 2rem);
}
```

Unidades como `cqi` e `cqb` dimensionam valores em relação a um query container elegível. Isso permite ao mesmo componente adaptar-se de forma independente em sidebar estreita e região principal larga. Container queries mais novas também podem testar style, scroll state e estado de posicionamento por âncora; use progressivamente e verifique suporte ao tipo exato de query.
