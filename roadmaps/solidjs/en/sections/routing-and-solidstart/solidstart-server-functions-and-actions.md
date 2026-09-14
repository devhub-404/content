# Server Functions and Actions

SolidStart server functions let application code invoke server-only logic through framework-managed transport, and router actions provide a mutation model that integrates with forms and data invalidation. They reduce the need to write a separate JSON endpoint for every internal mutation.

```tsx
const saveTodo = action(async formData => {
  "use server";
  const title = String(formData.get("title"));
  await db.todos.create({ title });
});

<form action={saveTodo}>
  <input name="title" />
  <button>Add</button>
</form>
```

They still cross a network boundary. Validate input, authenticate, authorize, and keep secrets on the server. Design duplicate submission and error behavior deliberately. Use explicit API routes when external clients need a durable HTTP contract independent of the Solid application.
