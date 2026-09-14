# `untrack`, `on`, and Explicit Dependency Control

Solid normally discovers dependencies automatically, but `on` can make a computation react to explicit sources and `untrack` can read a reactive value without subscribing the current tracking scope to it. These are precise tools for advanced dependency control.

```tsx
createEffect(on(userId, id => {
  const themeNow = untrack(theme);
  console.log("user changed", id, themeNow);
}));
```

Do not use them to silence reactivity you have not understood. If a value truly affects the computation's result, it should usually be a dependency. `untrack` is useful for incidental reads such as logging or one-time context, while `on` is useful when the dependency boundary itself is part of the design.
