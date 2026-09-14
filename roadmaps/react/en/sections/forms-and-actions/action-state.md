# Action State with `useActionState`

`useActionState` couples an action with the state returned by its previous execution and a pending flag. It works well when a submission needs to display server validation errors, returned data, or progress without manually wiring several independent pieces of state.

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

Keep the returned action state serializable when it must cross a server/client boundary, and model expected validation failures separately from unexpected exceptions. Disable or otherwise guard repeated submissions when duplicate execution would create harmful side effects.
