# React Compiler y Memoization Automática

React Compiler analiza components y Hooks para aplicar memoization automáticamente donde sus garantías lo permiten. Esto reduce la necesidad de dispersar `useMemo`, `useCallback` y `memo`, manteniendo el código normal legible.

```jsx
// Ordinary component code; the compiler can optimize supported patterns.
function ProductList({ products, query }) {
  const visible = products.filter(product => product.name.includes(query));
  return visible.map(product => <Product key={product.id} product={product} />);
}
```

El soporte depende del build y de seguir las Rules of React. Trata los diagnostics como señales de corrección en vez de luchar con escape hatches. La memoization manual aún puede servir en boundaries explícitas, pero mide antes.
