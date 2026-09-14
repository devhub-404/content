# Store Updates, `produce` e `reconcile`

Store setters suportam path syntax e updaters. `produce` oferece syntax mutation-style aplicando a mudança pelo store, e `reconcile` pode mesclar dados novos preservando referências existentes quando values correspondem.

```tsx
setState(
  produce(draft => {
    draft.todos.push({ id: 1, title: "Learn Solid" });
  })
);

setState("users", reconcile(serverUsers, { key: "id" }));
```

Escolha update form que torna transição mais clara. Reconciliation ajuda server snapshots/lists, mas key e merge semantics importam. Não use helper profundo apenas para evitar entender qual parte realmente mudou.
