# Data Fetching Paralelo y Secuencial

Await de data independiente una por una crea waterfall. Inicia operations independientes juntas y usa `Promise.all`, manteniendo trabajo realmente dependiente secuencial. Component composition también puede iniciar data concurrente en branches distintos.

```tsx
const userPromise = getUser(id);
const postsPromise = getPosts(id);

const [user, posts] = await Promise.all([
  userPromise,
  postsPromise
]);
```

Paralelo no es automáticamente más barato: una page puede sobrecargar DB/API con demasiadas operations. Agrupa cuando el backend lo permita y usa Suspense boundaries cuando partes puedan streamear independientemente.
