# UI de Submission con `useFormStatus`

`useFormStatus` permite que un component dentro de un form lea el estado del submit del form parent más cercano. Es útil para submit buttons reutilizables, spinners y feedback contextual sin pasar pending props por varios levels.

```jsx
function SubmitButton() {
  const { pending } = useFormStatus();
  return <button disabled={pending}>{pending ? 'Saving…' : 'Save'}</button>;
}

function Form() {
  return <form action={save}><SubmitButton /></form>;
}
```

El Hook observa el parent form, por lo que la posición en el tree importa. Mantén feedback cerca de la acción disparada y no deshabilites áreas no relacionadas. El status accesible debe seguir siendo comprensible para screen readers y keyboard users.
