# Dependencies y Cleanup de Effects

La dependency list describe los valores reactivos que el Effect lee del scope del component. No es un scheduler escrito manualmente. Cuando cambia una dependency, React limpia la sincronización anterior y ejecuta setup con los valores del nuevo render.

```jsx
useEffect(() => {
  const controller = new AbortController();

  fetch(`/api/users/${userId}`, { signal: controller.signal })
    .then(response => response.json())
    .then(setUser);

  return () => controller.abort();
}, [userId]);
```

No silencies el linter solo para evitar reruns. Reestructura para que el Effect lea exactamente lo que pertenece a la sincronización. Cleanup debe deshacer setup: unsubscribe, abort, disconnect, quitar listeners o liberar la relación externa.
