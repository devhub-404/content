# Action State con `useActionState`

`useActionState` asocia una action con el state retornado por la ejecución anterior y un pending flag. Funciona bien cuando un submit debe mostrar validation errors del servidor, datos retornados o progreso sin varios states manuales.

```jsx
function Signup() {
  const [state, submit, pending] = useActionState(registerUser, { error: null });

  return (
    <form action={submit}>
      <input name="email" type="email" />
      <button disabled={pending}>Create account</button>
      {state.error && <p>{state.error}</p>}
    </form>
  );
}
```

Mantén action state serializable cuando cruza server/client boundary y separa validation failures esperados de exceptions inesperadas. Deshabilita o protege repeated submits cuando una ejecución duplicada pueda causar side effects dañinos.
