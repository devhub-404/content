# Directive `use cache`

Directive `use cache` marca function/component/module cujo resultado pode ser reutilizado entre requests segundo cache key/lifetime. Pode cachear async work comum como database calls, não só `fetch`.

```tsx
import { cacheLife, cacheTag } from "next/cache";

export async function getProducts() {
  "use cache";
  cacheLife("hours");
  cacheTag("products");
  return db.product.findMany();
}
```

Cacheie apenas resultados seguros para callers compartilhando a mesma key. Values dependentes de cookies/headers/private user state não devem ficar em cache compartilhado amplo. Passe argumentos explícitos como parte da identity e mantenha secrets fora do output.
