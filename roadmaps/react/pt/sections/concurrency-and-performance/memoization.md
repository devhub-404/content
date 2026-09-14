# Memoization com `memo`, `useMemo` e `useCallback`

Memoization pode evitar cálculos ou component work repetidos quando inputs não mudam. `useMemo` cacheia valor calculado, `useCallback` identidade de function e `memo` permite reutilizar resultado anterior quando props comparam iguais.

```jsx
const FilteredList = memo(function FilteredList({ items, query }) {
  const visible = useMemo(
    () => items.filter(item => item.name.includes(query)),
    [items, query]
  );

  return visible.map(item => <p key={item.id}>{item.name}</p>);
});
```

Trate como ferramenta de performance, não correção. Meça antes de espalhar memoization. React Compiler pode remover muita memoization manual em setups suportados, e state ownership claro ou components menores frequentemente resolvem melhor que caches por toda parte.
