# Parallel and Sequential Data Fetching

Awaiting independent data one request at a time creates waterfalls. Start independent operations together and await them in parallel, while keeping genuinely dependent work sequential. Component composition can also start data in different branches concurrently.

```tsx
const userPromise = getUser(id);
const postsPromise = getPosts(id);

const [user, posts] = await Promise.all([
  userPromise,
  postsPromise
]);
```

Parallel work is not automatically cheaper: a page can overload a database or external API by launching too many expensive operations. Batch or aggregate requests when the backend supports it, and use Suspense boundaries when parts of the route can stream independently instead of blocking on every value.
