# UI de Submission com `useFormStatus`

`useFormStatus` permite que component dentro de form leia status do submit do form parent mais próximo. É útil para submit buttons reutilizáveis, spinners e feedback contextual sem passar pending props por vários levels.

```jsx
function SubmitButton() {
  const { pending } = useFormStatus();
  return <button disabled={pending}>{pending ? 'Saving…' : 'Save'}</button>;
}

function Form() {
  return <form action={save}><SubmitButton /></form>;
}
```

O Hook observa o parent form, então posição na tree importa. Mantenha feedback perto da ação disparada e não desabilite áreas sem relação. Status acessível precisa permanecer compreensível a screen readers e keyboard users.
