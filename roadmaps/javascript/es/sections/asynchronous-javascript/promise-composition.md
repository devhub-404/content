# Composición de Promises

`Promise.all()` requiere que todos los inputs tengan éxito y rechaza en el primer fallo. `allSettled()` espera todos los resultados. `race()` toma el primer settlement y `any()` el primer fulfillment, rechazando solo si todos fallan.

```js
const [user, settings] = await Promise.all([
  loadUser(),
  loadSettings(),
]);

const first = await Promise.any([
  fetchFromPrimary(),
  fetchFromReplica(),
]);
```

Iniciar operaciones independientes antes de esperar permite concurrencia; waits consecutivos pueden serializar sin querer. Los combinators no cancelan operaciones restantes automáticamente. El cancelamiento depende de la API del host, como `AbortController` en Fetch.
