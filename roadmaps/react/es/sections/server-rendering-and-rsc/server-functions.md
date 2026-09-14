# Server Functions

Una Server Function es una async function ejecutada en server que puede ser referenciada por código client compatible mediante un framework React. `'use server'` marca estas functions callable; no marca Server Components.

```jsx
// actions.js
'use server';

export async function renameUser(formData) {
  const name = formData.get('name');
  await db.users.rename(name);
}
```

Las Server Functions cruzan una network boundary aunque parezcan una function call. Autentica/autoriza dentro, valida argumentos, no retornes secrets y diseña idempotency/duplicate submission. El framework gestiona transport, routing y serialization.
