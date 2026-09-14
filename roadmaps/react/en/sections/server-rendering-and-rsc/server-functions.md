# Server Functions

A Server Function is an async function executed on the server that can be referenced from compatible client code through a React framework. The `'use server'` directive marks these callable server functions; it does not mark Server Components themselves.

```jsx
// actions.js
'use server';

export async function renameUser(formData) {
  const name = formData.get('name');
  await db.users.rename(name);
}
```

Server Functions cross a network boundary even when they look like function calls. Authenticate and authorize inside the function, validate all arguments, avoid returning secrets, and design idempotency or duplicate-submission behavior deliberately. Framework implementations handle transport, routing, and serialization details.
