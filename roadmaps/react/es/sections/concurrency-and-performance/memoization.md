# Memoization con `memo`, `useMemo` y `useCallback`

La memoization puede evitar cálculos o component work repetidos cuando los inputs no cambian. `useMemo` cachea un valor calculado, `useCallback` la identidad de una function y `memo` permite reutilizar el resultado anterior cuando las props comparan iguales.

```jsx
const FilteredList = memo(function FilteredList({ items, query }) {
  const visible = useMemo(
    () => items.filter(item => item.name.includes(query)),
    [items, query]
  );

  return visible.map(item => <p key={item.id}>{item.name}</p>);
});
```

Trátalos como herramientas de performance, no de corrección. Mide antes de extender memoization. React Compiler puede eliminar mucha memoization manual en setups soportados y un state ownership claro o components menores suelen resolver mejor que caches por todas partes.
