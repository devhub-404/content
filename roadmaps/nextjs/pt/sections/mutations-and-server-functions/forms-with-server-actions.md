# Forms com Server Actions

Passar Server Action a `form action` conecta native submit a execução server. `FormData` preserva semântica HTML e React/Next pode retornar UI atualizada no mesmo round trip com progressive enhancement.

```tsx
<form action={createTodo}>
  <label>
    Title
    <input name="title" required />
  </label>
  <button>Add todo</button>
</form>
```

Comece por form HTML válido com labels/names/required e server validation. Client validation só melhora feedback. Projete duplicate submission, principalmente payments/invites e mutations que precisam idempotency.
