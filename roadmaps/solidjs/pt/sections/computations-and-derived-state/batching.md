# Batching de Updates

`batch` agrupa vários writes reativos para downstream computations observarem o conjunto final em vez de rodar após cada setter. Solid já faz batching em algumas situações, mas batching explícito ajuda quando uma operação lógica faz múltiplos writes independentes.

```tsx
const [first, setFirst] = createSignal("Ada");
const [last, setLast] = createSignal("Lovelace");

batch(() => {
  setFirst("Grace");
  setLast("Hopper");
});
```

Use para representar uma state transition única, não para esconder state excessivamente fragmentado. Fine-grained reactivity já minimiza trabalho; meça antes de adicionar batch apenas por performance. Correctness não deve depender de estados intermediários impossíveis.
