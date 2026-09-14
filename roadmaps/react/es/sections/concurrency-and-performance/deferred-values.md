# Deferred Values

`useDeferredValue` proporciona una versión retrasada de un valor que puede actualizar a menor prioridad. Es útil cuando el parent ya posee state urgente pero un child lento debe mantener el resultado anterior mientras se prepara el nuevo render.

```jsx
function Results({ query }) {
  const deferredQuery = useDeferredValue(query);
  const stale = query !== deferredQuery;

  return <SearchResults query={deferredQuery} dimmed={stale} />;
}
```

Deferred value no retrasa requests por sí solo ni ofrece un timeout fijo; difiere rendering. Úsalo cuando conservar la UI anterior sea mejor que bloquear input o sustituir contenido útil por loading inmediatamente.
