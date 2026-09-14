# Datos Async con `createResource`

`createResource` conecta un async fetcher a una source reactiva y expone el resultado como accessor con loading/error state. Cuando cambia la source, Solid puede volver a ejecutar el fetcher e integrar el pending result con rendering mediante Suspense.

```tsx
const [userId, setUserId] = createSignal(1);

const [user] = createResource(userId, async id => {
  const response = await fetch(`/api/users/${id}`);
  return response.json();
});

<Show when={user()}>{value => <h1>{value().name}</h1>}</Show>
```

Usa resources para valores async que pertenecen al reactive graph en vez de varios signals manuales. Define cancellation, stale data, error y refetch según la source real. En SolidStart full-stack, router queries ofrecen un modelo de loading más alto.
