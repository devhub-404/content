# Tracking Scopes and Dependency Graphs

Reactive dependencies are discovered while a tracking computation runs. If that computation reads `price()` and `quantity()`, Solid records those edges and reruns only the affected work when one source changes. Dependencies can also change dynamically between executions.

```tsx
const [price, setPrice] = createSignal(10);
const [quantity, setQuantity] = createSignal(2);

const total = createMemo(() => price() * quantity());

createEffect(() => {
  console.log("total", total());
});
```

This graph is created at runtime, so keep reactive reads inside the computation that should depend on them. Reading a signal outside a tracking scope gives a plain current value. That distinction explains many bugs where a value seems to “stop being reactive.”
