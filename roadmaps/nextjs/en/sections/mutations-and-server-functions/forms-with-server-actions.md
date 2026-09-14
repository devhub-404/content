# Forms with Server Actions

Passing a Server Action to a form's `action` prop connects native form submission to server execution. `FormData` preserves standard HTML form semantics, and React/Next can return updated UI in the same round trip while still supporting progressive-enhancement behavior.

```tsx
<form action={createTodo}>
  <label>
    Title
    <input name="title" required />
  </label>
  <button>Add todo</button>
</form>
```

Start from a valid HTML form: labels, names, required fields, and server validation. Client-side validation improves feedback but cannot protect the server. Design duplicate-submission behavior, especially for payments, invitations, and other mutations that must be idempotent or uniquely keyed.
