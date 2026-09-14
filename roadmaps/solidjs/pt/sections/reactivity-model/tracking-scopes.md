# Tracking Scopes e Dependency Graphs

Reactive dependencies são descobertas enquanto um tracking computation executa. Se ele lê `price()` e `quantity()`, Solid registra essas edges e roda novamente apenas o trabalho afetado quando source muda. Dependencies também podem mudar dinamicamente.

```tsx
const [price, setPrice] = createSignal(10);
const [quantity, setQuantity] = createSignal(2);

const total = createMemo(() => price() * quantity());

createEffect(() => {
  console.log("total", total());
});
```

O graph é criado em runtime, então mantenha reactive reads dentro do computation que deve depender delas. Ler signal fora de tracking scope fornece valor atual comum. Essa distinção explica muitos bugs em que valor parece “parar de ser reativo”.
