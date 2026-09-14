# Directive `use cache`

La directive `use cache` marca una function/component/module cuyo resultado puede reutilizarse entre requests según cache key/lifetime. Puede cachear async work normal como database calls, no solo `fetch`.

```tsx
import { cacheLife, cacheTag } from "next/cache";

export async function getProducts() {
  "use cache";
  cacheLife("hours");
  cacheTag("products");
  return db.product.findMany();
}
```

Cachea solo resultados seguros para callers que comparten la misma key. Values dependientes de cookies/headers/private user state no deben quedar en una cache compartida amplia. Pasa argumentos explícitos como parte de identity y mantén secrets fuera del output.
