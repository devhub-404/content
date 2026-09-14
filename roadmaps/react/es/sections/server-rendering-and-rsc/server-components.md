# React Server Components

Un Server Component renderiza en un entorno server/build antes de que el resultado llegue al client. Puede acceder a datos/dependencies del servidor directamente y no añade su component code al client bundle. Los Server Components pueden ser async.

```jsx
async function Note({ id }) {
  const note = await db.notes.get(id);
  return <article>{note.body}</article>;
}
```

No pueden usar Hooks de interacción client como `useState`. Se componen con Client Components cuando la UI necesita browser APIs/events. React define el modelo, pero una aplicación normalmente usa RSC mediante un framework que implementa bundling y transport.
