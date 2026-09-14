# Reactive Owners y `createRoot`

Las reactive computations pertenecen a owners que controlan cleanup/lifetime. Los components crean ownership scopes automáticamente, mientras `createRoot` los crea manualmente para reactive systems fuera de component rendering. Disponer el root limpia computations/resources bajo él.

```tsx
const dispose = createRoot(dispose => {
  const [count, setCount] = createSignal(0);
  createEffect(() => console.log(count()));
  setCount(1);
  return dispose;
});

dispose();
```

Entender ownership evita leaked effects/resources. Si creas reactive work en callback/library fuera de un owner, define quién lo dispone. Helpers como `getOwner`/`runWithOwner` preservan contexto, pero el ownership normal de component es más simple cuando está disponible.
