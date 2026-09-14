# `cacheLife` e `cacheTag`

`cacheLife` escolhe freshness/revalidation/expiration e `cacheTag` associa tags semânticas às cache entries. Juntos expressam quanto reuse é aceitável e quais domain events invalidam dados relacionados.

```tsx
import { cacheLife, cacheTag } from "next/cache";

async function getPost(slug) {
  "use cache";
  cacheLife("hours");
  cacheTag("posts", `post:${slug}`);
  return db.post.findUnique({ where: { slug } });
}
```

Dê tags por domain identity como `products` ou `post:slug`, não por UI component. Cache lifetime é decisão de product freshness, não só performance. Curto demais pode sobrecarregar backend; longo demais pode servir data incorreta.
