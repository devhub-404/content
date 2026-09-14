# Store Updates, `produce` y `reconcile`

Los store setters soportan path syntax y updaters. `produce` ofrece syntax mutation-style aplicando el cambio mediante el store, y `reconcile` puede mezclar datos nuevos conservando referencias existentes cuando los values coinciden.

```tsx
setState(
  produce(draft => {
    draft.todos.push({ id: 1, title: "Learn Solid" });
  })
);

setState("users", reconcile(serverUsers, { key: "id" }));
```

Elige la update form que haga más clara la transición. Reconciliation ayuda con server snapshots/lists, pero key y merge semantics importan. No uses un helper profundo solo para evitar entender qué parte cambió realmente.
