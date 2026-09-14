# Store Updates, `produce`, and `reconcile`

Store setters support path syntax and updater functions. `produce` provides mutation-style syntax while applying the change through the store, and `reconcile` can merge new structured data while preserving existing references where values match.

```tsx
setState(
  produce(draft => {
    draft.todos.push({ id: 1, title: "Learn Solid" });
  })
);

setState("users", reconcile(serverUsers, { key: "id" }));
```

Choose the update form that makes the domain transition easiest to understand. Reconciliation is useful for server snapshots or normalized lists, but key selection and merge semantics matter. Do not use a deep helper merely to avoid learning which part of the state actually changed.
