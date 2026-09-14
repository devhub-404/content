# Dados Async com `createResource`

`createResource` conecta async fetcher a source reativa e expõe resultado como accessor com loading/error state. Quando source muda, Solid pode rodar fetcher novamente e integrar pending result ao rendering com Suspense.

```tsx
const [userId, setUserId] = createSignal(1);

const [user] = createResource(userId, async id => {
  const response = await fetch(`/api/users/${id}`);
  return response.json();
});

<Show when={user()}>{value => <h1>{value().name}</h1>}</Show>
```

Use resources para valores async que pertencem ao reactive graph em vez de vários signals manuais. Defina cancellation, stale data, error e refetch conforme source real. Em SolidStart full-stack, router queries oferecem modelo de loading mais alto.
