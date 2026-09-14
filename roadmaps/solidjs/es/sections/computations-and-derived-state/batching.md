# Batching de Updates

`batch` agrupa varios writes reactivos para que downstream computations observen el conjunto final en vez de ejecutarse tras cada setter. Solid ya hace batching en varias situaciones, pero el batching explícito ayuda cuando una operación lógica realiza varios writes independientes.

```tsx
const [first, setFirst] = createSignal("Ada");
const [last, setLast] = createSignal("Lovelace");

batch(() => {
  setFirst("Grace");
  setLast("Hopper");
});
```

Úsalo para representar una state transition única, no para ocultar state demasiado fragmentado. Fine-grained reactivity ya minimiza trabajo; mide antes de añadir batch solo por performance. La correctness no debería depender de estados intermedios imposibles.
