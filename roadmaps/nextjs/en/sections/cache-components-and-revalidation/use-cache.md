# The `use cache` Directive

The `use cache` directive marks a function, component, or compatible module scope whose result can be reused across requests according to the cache key and lifetime rules. It can cache ordinary async work such as database calls, not only `fetch`.

```tsx
import { cacheLife, cacheTag } from "next/cache";

export async function getProducts() {
  "use cache";
  cacheLife("hours");
  cacheTag("products");
  return db.product.findMany();
}
```

Cache only results that are safe for callers sharing the same key. Values that depend on cookies, headers, or private per-user state should not be hidden inside a broad shared cache. Pass explicit arguments when they are part of cache identity and keep secrets out of cached output.
