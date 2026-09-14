# `cacheLife` y `cacheTag`

`cacheLife` elige freshness/revalidation/expiration y `cacheTag` asocia tags semánticas a cache entries. Juntos expresan cuánto reuse es aceptable y qué domain events invalidan datos relacionados.

```tsx
import { cacheLife, cacheTag } from "next/cache";

async function getPost(slug) {
  "use cache";
  cacheLife("hours");
  cacheTag("posts", `post:${slug}`);
  return db.post.findUnique({ where: { slug } });
}
```

Nombra tags por domain identity como `products` o `post:slug`, no por UI component. Cache lifetime es una decisión de product freshness, no solo performance. Demasiado corto puede sobrecargar backend; demasiado largo puede servir datos incorrectos.
