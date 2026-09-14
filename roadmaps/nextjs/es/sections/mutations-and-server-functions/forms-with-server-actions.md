# Forms con Server Actions

Pasar una Server Action a `form action` conecta native submit con ejecución server. `FormData` conserva semántica HTML y React/Next puede retornar UI actualizada en el mismo round trip con progressive enhancement.

```tsx
<form action={createTodo}>
  <label>
    Title
    <input name="title" required />
  </label>
  <button>Add todo</button>
</form>
```

Empieza con un form HTML válido con labels/names/required y server validation. Client validation solo mejora feedback. Diseña duplicate submission, especialmente payments/invites y mutations que necesitan idempotency.
