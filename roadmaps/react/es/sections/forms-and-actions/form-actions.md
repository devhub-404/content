# Form Actions

Los forms React pueden recibir una function en `action`. Recibe `FormData` y React coordina submission state y reset. En frameworks con Server Functions, el mismo modelo puede enviar directamente a lógica del servidor con progressive enhancement.

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

Usa fields y names nativos para que el browser construya `FormData` útil. Trata las actions del servidor como request handlers públicos: autentica, autoriza y valida datos; no confíes solo porque el form vino de tu propia app.
