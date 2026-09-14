# List Rendering with `For` and `Index`

`For` maps list items by identity and is the normal choice when rows represent objects that may move, be inserted, or be removed. The item is stable while the index is a reactive accessor. `Index` instead keys by position and makes each value reactive.

```tsx
<For each={users()}>
  {(user, index) => (
    <p>{index() + 1}. {user.name}</p>
  )}
</For>
```

Choose based on what is stable in your data. For records with identity, `For` usually matches the domain. For primitive values where positions are fixed but values change, `Index` may avoid unnecessary row recreation. Do not mechanically translate React key patterns into Solid.
