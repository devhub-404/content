# Custom Reactive Primitives

Reusable Solid logic is usually expressed as an ordinary function that creates and returns signals, stores, resources, memos, effects, or callbacks. Because primitives use ownership and tracking rather than component-only Hook rules, these helpers can be composed naturally.

```tsx
function createToggle(initial = false) {
  const [value, setValue] = createSignal(initial);
  const toggle = () => setValue(current => !current);
  return [value, toggle];
}

const [open, toggleOpen] = createToggle();
```

Design a primitive around one coherent behavior and return the smallest useful API. Preserve getter functions when callers need reactivity instead of exposing snapshots. If the primitive creates external subscriptions or owned computations, register cleanup so its lifetime follows the owner that called it.
