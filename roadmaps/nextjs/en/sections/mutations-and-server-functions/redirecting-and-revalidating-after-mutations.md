# Redirecting and Revalidating after Mutations

After a mutation, a Server Action can invalidate affected cached data and redirect to the canonical result page. Next.js can combine the mutation and route refresh efficiently, so the destination sees server-rendered data consistent with the invalidation rules.

```tsx
"use server";

export async function createPost(formData: FormData) {
  const post = await savePost(formData);
  revalidatePath("/posts");
  redirect(`/posts/${post.slug}`);
}
```

Perform the durable mutation before invalidating or redirecting. Keep invalidation targeted to the domain that changed. `redirect` changes control flow rather than behaving like an ordinary return value, so place cleanup and transaction handling where they will still run correctly.
