# Queries y Data Loading en SolidStart

SolidStart v2 usa queries de Solid Router para data loading cacheado y `createAsync` para leer results async reactivamente. Una query puede usar la directive `use server` para que el acceso sensible se ejecute solo en server mientras la route consume el resultado mediante el framework.

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

Mantén data functions cerca de las domain boundaries y trata cache identity como parte de la API. Loading, errors, revalidation y mutation deben formar un modelo coherente en vez de fetch Effects ad-hoc. Authorization sigue siendo obligatoria en server.
