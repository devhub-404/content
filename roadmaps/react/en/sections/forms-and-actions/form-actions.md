# Form Actions

React forms can receive a function in the `action` prop. The function receives `FormData`, and React coordinates submission state and form resetting behavior. In frameworks that support Server Functions, the same form model can submit directly to server-executed logic with progressive enhancement.

```jsx
async function saveProfile(formData) {
  const name = formData.get('name');
  await updateProfile({ name });
}

function ProfileForm() {
  return (
    <form action={saveProfile}>
      <input name="name" />
      <button>Save</button>
    </form>
  );
}
```

Use native form fields and names so the browser can construct meaningful `FormData`. Treat server-executed actions as public request handlers: authenticate, authorize, validate all data, and do not trust values merely because the form was rendered by your own application.
