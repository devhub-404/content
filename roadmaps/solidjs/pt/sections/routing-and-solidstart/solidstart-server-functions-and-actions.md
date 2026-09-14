# Server Functions e Actions

Server functions do SolidStart permitem invocar lógica server-only por transport gerenciado pelo framework, e router actions oferecem mutation model integrado a forms e invalidation. Isso reduz necessidade de endpoint JSON separado para toda mutation interna.

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

Ainda atravessam network boundary. Valide input, autentique, autorize e mantenha secrets no server. Projete duplicate submission/errors. Use API routes explícitas quando external clients precisam contrato HTTP independente do app Solid.
