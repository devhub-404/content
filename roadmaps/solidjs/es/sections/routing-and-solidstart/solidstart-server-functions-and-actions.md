# Server Functions y Actions

Las server functions de SolidStart permiten invocar lógica server-only mediante transport gestionado por el framework, y las router actions ofrecen un mutation model integrado con forms e invalidation. Esto reduce la necesidad de un endpoint JSON separado para cada mutation interna.

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

Siguen cruzando una network boundary. Valida input, autentica, autoriza y mantén secrets en server. Diseña duplicate submission/errors. Usa API routes explícitas cuando external clients necesiten un contrato HTTP independiente de la app Solid.
