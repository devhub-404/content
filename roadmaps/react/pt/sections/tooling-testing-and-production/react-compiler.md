# React Compiler e Memoization Automática

React Compiler analisa components e Hooks para aplicar memoization automaticamente onde suas guarantees permitem. Isso reduz necessidade de espalhar `useMemo`, `useCallback` e `memo`, mantendo código comum legível.

```jsx
// Ordinary component code; the compiler can optimize supported patterns.
function ProductList({ products, query }) {
  const visible = products.filter(product => product.name.includes(query));
  return visible.map(product => <Product key={product.id} product={product} />);
}
```

Suporte depende do build e de seguir Rules of React. Trate diagnostics como sinais de correção em vez de lutar com escape hatches. Memoization manual ainda pode servir em boundaries explícitas, mas meça antes.
