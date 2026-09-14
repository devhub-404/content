# Effects

`createEffect` runs side-effecting code in response to reactive dependencies. It tracks signals and other reactive values read during execution, rerunning after those dependencies change. Effects are intended for synchronizing with the outside world, not for ordinary derived values.

```tsx
const [theme, setTheme] = createSignal("dark");

createEffect(() => {
  document.documentElement.dataset.theme = theme();
});
```

Prefer memos or direct reactive expressions for computation. Inside an effect, keep the external action focused and pair subscriptions or resources with `onCleanup`. An effect that only writes another signal often indicates that the state relationship can be modeled more directly.
