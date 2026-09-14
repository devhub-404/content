# Reactive Owners e `createRoot`

Reactive computations pertencem a owners que controlam cleanup/lifetime. Components criam ownership scopes automaticamente, enquanto `createRoot` cria manualmente para reactive systems fora de component rendering. Dispor root limpa computations/resources abaixo dele.

```tsx
const dispose = createRoot(dispose => {
  const [count, setCount] = createSignal(0);
  createEffect(() => console.log(count()));
  setCount(1);
  return dispose;
});

dispose();
```

Entender ownership evita leaked effects/resources. Se criar reactive work em callback/library fora de owner, defina quem dispõe. Helpers como `getOwner`/`runWithOwner` preservam contexto, mas ownership normal de component é mais simples quando disponível.
