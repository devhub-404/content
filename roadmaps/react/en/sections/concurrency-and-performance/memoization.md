# Memoization with `memo`, `useMemo`, and `useCallback`

Memoization can skip repeated calculations or component work when inputs are unchanged. `useMemo` caches a calculated value, `useCallback` caches a function identity, and `memo` lets a component reuse its previous rendered result when its props compare equal.

```jsx
const FilteredList = memo(function FilteredList({ items, query }) {
  const visible = useMemo(
    () => items.filter(item => item.name.includes(query)),
    [items, query]
  );

  return visible.map(item => <p key={item.id}>{item.name}</p>);
});
```

Treat these as performance tools, not correctness tools. Measure before spreading memoization across every component. The React Compiler can remove much manual memoization in supported setups, and clear state ownership or smaller component boundaries often solve performance problems more effectively than adding caches everywhere.
