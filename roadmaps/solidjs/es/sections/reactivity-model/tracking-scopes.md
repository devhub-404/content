# Tracking Scopes y Dependency Graphs

Las reactive dependencies se descubren mientras se ejecuta una tracking computation. Si lee `price()` y `quantity()`, Solid registra esas edges y vuelve a ejecutar solo el trabajo afectado cuando cambia una source. Las dependencies también pueden cambiar dinámicamente.

```tsx
const [price, setPrice] = createSignal(10);
const [quantity, setQuantity] = createSignal(2);

const total = createMemo(() => price() * quantity());

createEffect(() => {
  console.log("total", total());
});
```

El graph se crea en runtime, así que mantén las reactive reads dentro de la computation que debe depender de ellas. Leer un signal fuera de un tracking scope da un valor actual normal. Esta distinción explica muchos bugs donde algo parece “dejar de ser reactivo”.
