# React Server Components

Server Component renderiza em ambiente server/build antes de o resultado chegar ao client. Pode acessar dados/dependencies de servidor diretamente e não adiciona seu component code ao client bundle. Server Components podem ser async.

```jsx
async function Note({ id }) {
  const note = await db.notes.get(id);
  return <article>{note.body}</article>;
}
```

Eles não podem usar Hooks de interação client como `useState`. Compõem com Client Components quando UI precisa de browser APIs/events. React define o modelo, mas aplicação normalmente usa RSC por framework que implementa bundling e transport.
