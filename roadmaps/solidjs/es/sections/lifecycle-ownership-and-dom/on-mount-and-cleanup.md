# `onMount` y `onCleanup`

`onMount` programa setup después de montar los elements iniciales y `onCleanup` registra cleanup en el reactive owner actual. Cleanup se ejecuta cuando ese owner se dispone, incluso cuando se elimina un component o branch condicional.

```tsx
onMount(() => {
  const controller = connect();
  controller.start();

  onCleanup(() => controller.stop());
});
```

Usa cleanup para listeners, subscriptions, timers, observers y recursos externos. No trates el body del component como callback repetido; es setup. Ownership y disposal, no rerender cycles, son los conceptos centrales de lifecycle.
