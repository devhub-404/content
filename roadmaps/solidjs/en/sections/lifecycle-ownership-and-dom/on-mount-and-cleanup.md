# `onMount` and `onCleanup`

`onMount` schedules setup after a component's initial elements are mounted, and `onCleanup` registers cleanup with the current reactive owner. Cleanup runs when that owner is disposed, which can happen because a component or conditional branch is removed.

```tsx
onMount(() => {
  const controller = connect();
  controller.start();

  onCleanup(() => controller.stop());
});
```

Use cleanup for event listeners, subscriptions, timers, observers, and external resources. Do not assume a component's function body is a repeated lifecycle callback; it is setup. Ownership and disposal, rather than rerender cycles, are the key lifecycle concepts in Solid.
