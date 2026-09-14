# Server Functions e Server Actions

Next usa React Server Functions para mutations server-side e chama Server Actions em action contexts como forms. São async functions chamadas por network mesmo que o código pareça function import normal.

```tsx
// app/actions.ts
"use server";

export async function createTodo(formData: FormData) {
  const title = String(formData.get("title"));
  await db.todo.create({ data: { title } });
}
```

Trate toda Server Function como externally reachable. Autentique, autorize, valide args, limite side effects e retorne values seguros. Coloque domain mutation em server modules para actions finas/testáveis.
