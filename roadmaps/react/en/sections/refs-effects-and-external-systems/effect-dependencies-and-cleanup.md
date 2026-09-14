# Effect Dependencies and Cleanup

The dependency list describes the reactive values an Effect reads from the component scope. It is not a hand-written schedule. When one dependency changes, React cleans up the previous synchronization and runs setup again with the new render's values.

```jsx
useEffect(() => {
  const controller = new AbortController();

  fetch(`/api/users/${userId}`, { signal: controller.signal })
    .then(response => response.json())
    .then(setUser);

  return () => controller.abort();
}, [userId]);
```

Do not silence the dependency linter simply to stop reruns. Instead, restructure code so the Effect reads exactly what belongs to the synchronization. Cleanup should undo the setup: unsubscribe, abort, disconnect, remove listeners, or otherwise release the external relationship.
