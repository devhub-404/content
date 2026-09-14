# `onMount` e `onCleanup`

`onMount` agenda setup após elements iniciais serem montados, e `onCleanup` registra cleanup no reactive owner atual. Cleanup roda quando owner é disposed, inclusive quando component ou branch condicional é removido.

```tsx
onMount(() => {
  const controller = connect();
  controller.start();

  onCleanup(() => controller.stop());
});
```

Use cleanup para listeners, subscriptions, timers, observers e recursos externos. Não trate function body do component como callback repetido; é setup. Ownership e disposal, não rerender cycles, são os conceitos centrais de lifecycle.
