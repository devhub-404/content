# Redirect y Revalidation después de Mutations

Después de una mutation, una Server Action puede invalidar cached data afectada y redirect a la canonical result page. Next combina mutation/route refresh de forma eficiente según invalidation rules.

```tsx
"use server";

export async function createPost(formData: FormData) {
  const post = await savePost(formData);
  revalidatePath("/posts");
  redirect(`/posts/${post.slug}`);
}
```

Haz la durable mutation antes de invalidar/redirect. Invalida el dominio específico. `redirect` cambia control flow en vez de retornar normalmente, así que organiza cleanup/transactions para que sigan siendo correctos.
