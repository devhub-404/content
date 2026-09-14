# Server Functions and Server Actions

Next.js uses React Server Functions for server-executed mutations and calls them Server Actions when used in action contexts such as forms. They are async network-callable functions even though application code can import and invoke them with function-like syntax.

```tsx
// app/actions.ts
"use server";

export async function createTodo(formData: FormData) {
  const title = String(formData.get("title"));
  await db.todo.create({ data: { title } });
}
```

Treat every Server Function as externally reachable. Authenticate, authorize, validate arguments, constrain side effects, and return only safe values. Put domain mutation logic in server modules so actions stay thin and can be tested independently of React transport.
