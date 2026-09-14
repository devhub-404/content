# Server Functions y Server Actions

Next usa React Server Functions para mutations server-side y las llama Server Actions en action contexts como forms. Son async functions llamadas por network aunque el código parezca un function import normal.

```tsx
// app/actions.ts
"use server";

export async function createTodo(formData: FormData) {
  const title = String(formData.get("title"));
  await db.todo.create({ data: { title } });
}
```

Trata cada Server Function como externally reachable. Autentica, autoriza, valida args, limita side effects y retorna values seguros. Pon domain mutation en server modules para actions delgadas/testeables.
