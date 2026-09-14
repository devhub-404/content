# Action State com `useActionState`

`useActionState` associa uma action ao state retornado pela execução anterior e a um pending flag. Funciona bem quando submit precisa mostrar validation errors do servidor, dados retornados ou progresso sem vários states manuais.

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

Mantenha action state serializável quando atravessa server/client boundary e separe validation failures esperadas de exceptions inesperadas. Desabilite ou proteja repeated submits quando execução duplicada causar side effects ruins.
