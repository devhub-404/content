# `revalidateTag`, `updateTag`, and `revalidatePath`

On-demand invalidation connects mutations to cached reads. `revalidateTag` marks tagged data for refresh with the selected profile, `updateTag` supports immediate read-your-own-writes style invalidation in relevant action flows, and `revalidatePath` targets route paths or layouts.

```tsx
"use server";

import { revalidateTag } from "next/cache";

export async function publishPost() {
  await db.post.publish();
  revalidateTag("posts", "max");
}
```

Invalidate the data domain that changed rather than clearing the entire application cache. Revalidation is not authorization or transaction isolation: commit the database change first, handle failures, then invalidate the relevant cached representation. Understand stale-while-revalidate behavior before promising users an immediate visible update.
