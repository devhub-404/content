# Form Actions

Forms React podem receber function em `action`. Ela recebe `FormData`, e React coordena submission state e reset. Em frameworks com Server Functions, o mesmo modelo pode enviar diretamente a lógica no servidor com progressive enhancement.

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

Use fields e names nativos para o browser construir `FormData` útil. Trate actions no servidor como request handlers públicos: autentique, autorize e valide dados; não confie porque o form veio do próprio app.
