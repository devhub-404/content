# Nested Submission UI with `useFormStatus`

`useFormStatus` lets a component rendered inside a form read the status of the nearest parent form submission. This is useful for reusable submit buttons, spinners, and contextual submission feedback without threading pending props through each form component.

```jsx
function SubmitButton() {
  const { pending } = useFormStatus();
  return <button disabled={pending}>{pending ? 'Saving…' : 'Save'}</button>;
}

function Form() {
  return <form action={save}><SubmitButton /></form>;
}
```

The Hook observes its parent form, so placement in the tree matters. Keep pending feedback close to the action the user triggered and avoid disabling unrelated parts of the page. Accessible status messages should remain understandable to screen-reader and keyboard users.
