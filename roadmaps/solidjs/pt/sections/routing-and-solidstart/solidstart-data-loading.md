# Queries e Data Loading no SolidStart

SolidStart v2 usa queries do Solid Router para data loading cacheado e `createAsync` para ler results async reativamente. Uma query pode usar a directive `use server` para que acesso sensível execute somente no server enquanto a route consome o resultado pelo framework.

```tsx
const getPosts = query(async () => {
  "use server";
  return db.posts.findMany();
}, "posts");

export default function Posts() {
  const posts = createAsync(() => getPosts());
  return <For each={posts()}>{post => <p>{post.title}</p>}</For>;
}
```

Mantenha data functions perto das domain boundaries e trate cache identity como parte da API. Loading, errors, revalidation e mutation devem formar modelo coerente em vez de fetch Effects ad-hoc. Authorization continua obrigatória no server.
