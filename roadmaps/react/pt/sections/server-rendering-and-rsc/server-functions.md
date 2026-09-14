# Server Functions

Server Function é async function executada no server que pode ser referenciada por código client compatível através de framework React. `'use server'` marca essas functions callable; não marca Server Components.

```jsx
// actions.js
'use server';

export async function renameUser(formData) {
  const name = formData.get('name');
  await db.users.rename(name);
}
```

Server Functions atravessam network boundary mesmo parecendo function call. Autentique/autorize dentro, valide argumentos, não retorne secrets e projete idempotency/duplicate submission. Framework cuida de transport, routing e serialization.
