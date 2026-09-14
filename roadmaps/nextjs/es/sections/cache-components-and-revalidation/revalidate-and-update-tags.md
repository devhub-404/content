# `revalidateTag`, `updateTag` y `revalidatePath`

On-demand invalidation conecta mutations con cached reads. `revalidateTag` marca tagged data para refresh, `updateTag` soporta invalidation inmediata en flows relevantes y `revalidatePath` apunta a route paths/layouts.

```tsx
"use server";

import { revalidateTag } from "next/cache";

export async function publishPost() {
  await db.post.publish();
  revalidateTag("posts", "max");
}
```

Invalida el dominio que cambió, no toda la app. Revalidation no es authorization ni transaction isolation: confirma DB change primero, maneja fallos y luego invalida la representación. Entiende stale-while-revalidate antes de prometer update visual inmediato.
