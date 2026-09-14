# React Compiler and Automatic Memoization

React Compiler analyzes components and Hooks to apply memoization automatically where its guarantees allow. This can reduce the need for manually scattering `useMemo`, `useCallback`, and `memo` across application code, while keeping ordinary component code readable.

```jsx
// Ordinary component code; the compiler can optimize supported patterns.
function ProductList({ products, query }) {
  const visible = products.filter(product => product.name.includes(query));
  return visible.map(product => <Product key={product.id} product={product} />);
}
```

Compiler support depends on the build setup and code following the Rules of React. Treat compiler diagnostics as correctness signals rather than fighting them with escape hatches. Manual memoization can still be appropriate at explicit API or performance boundaries, but measure before adding it.
