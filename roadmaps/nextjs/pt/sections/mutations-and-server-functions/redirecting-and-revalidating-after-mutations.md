# Redirect e Revalidation após Mutations

Após mutation, Server Action pode invalidar cached data afetada e redirect para canonical result page. Next combina mutation/route refresh de forma eficiente conforme invalidation rules.

```tsx
"use server";

export async function createPost(formData: FormData) {
  const post = await savePost(formData);
  revalidatePath("/posts");
  redirect(`/posts/${post.slug}`);
}
```

Faça durable mutation antes de invalidar/redirect. Invalide domínio específico. `redirect` muda control flow em vez de retornar normalmente, então organize cleanup/transactions para continuarem corretos.
