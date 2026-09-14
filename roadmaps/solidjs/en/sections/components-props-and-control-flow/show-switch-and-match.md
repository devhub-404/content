# Conditional UI with `Show`, `Switch`, and `Match`

Solid's control-flow components preserve fine-grained reactivity while mounting and disposing UI according to conditions. `Show` handles one condition plus optional fallback, while `Switch` and `Match` express the first matching branch among several alternatives.

```tsx
<Show when={user()} fallback={<Login />}>
  {current => <Profile user={current()} />}
</Show>

<Switch>
  <Match when={status() === "loading"}>Loading…</Match>
  <Match when={status() === "error"}>Failed</Match>
</Switch>
```

These primitives are preferable to many raw JSX conditional expressions when they make ownership and branch lifetime clearer. The callback form of `Show` can provide a narrowed accessor for the truthy value, avoiding repeated reads and improving TypeScript inference.
