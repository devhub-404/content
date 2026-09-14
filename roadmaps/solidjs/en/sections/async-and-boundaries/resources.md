# Async Data with `createResource`

`createResource` connects an async fetcher to a reactive source and exposes the result as a reactive accessor with loading and error state. When the source changes, Solid can run the fetcher again and integrate the pending result with Suspense-aware rendering.

```tsx
const [userId, setUserId] = createSignal(1);

const [user] = createResource(userId, async id => {
  const response = await fetch(`/api/users/${id}`);
  return response.json();
});

<Show when={user()}>{value => <h1>{value().name}</h1>}</Show>
```

Use resources for async values that belong to the reactive graph rather than manually juggling several signals. Define cancellation, stale-data, error, and refetch behavior according to the real data source. In full-stack SolidStart applications, router queries provide a higher-level data-loading model.
