# SolidStart Queries and Data Loading

SolidStart v2 uses Solid Router queries for cached data loading and `createAsync` for reading async query results reactively. A query can be marked with the `use server` directive so sensitive data access executes only on the server while the route consumes the result through the framework.

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

Keep data functions close to domain boundaries and treat cache identity as part of the API. Loading, errors, revalidation, and mutation should form one coherent data model rather than independent ad-hoc fetch Effects in components. Validate authorization on the server regardless of what route rendered the UI.
