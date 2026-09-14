# `cacheLife` and `cacheTag`

`cacheLife` chooses or defines freshness, revalidation, and expiration behavior for cached work, while `cacheTag` associates semantic tags with cache entries. Together they express how long reuse is acceptable and which domain events should invalidate related data.

```tsx
import { cacheLife, cacheTag } from "next/cache";

async function getPost(slug) {
  "use cache";
  cacheLife("hours");
  cacheTag("posts", `post:${slug}`);
  return db.post.findUnique({ where: { slug } });
}
```

Name tags from domain identity such as `products`, `post:slug`, or `account:id` rather than UI components. A cache lifetime is a product freshness decision, not simply a performance number. Shorter is not always safer if it overloads backends, and longer is not acceptable for data that must update immediately.
