# `revalidateTag`, `updateTag` e `revalidatePath`

On-demand invalidation conecta mutations a cached reads. `revalidateTag` marca tagged data para refresh, `updateTag` suporta invalidation imediata em flows relevantes e `revalidatePath` mira route paths/layouts.

```tsx
"use server";

import { revalidateTag } from "next/cache";

export async function publishPost() {
  await db.post.publish();
  revalidateTag("posts", "max");
}
```

Invalide o domínio que mudou, não app inteira. Revalidation não é authorization nem transaction isolation: confirme DB change primeiro, trate falhas e então invalide representação. Entenda stale-while-revalidate antes de prometer update visual imediato.
