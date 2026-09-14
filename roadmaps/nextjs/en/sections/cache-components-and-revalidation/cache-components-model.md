# Cache Components Model

With `cacheComponents` enabled, Next.js can mix prerendered static shells, explicitly cached work, and uncached request-time work within one route. Dynamic data is not automatically baked into a prerender; cached regions opt in through the cache model and dynamic regions stream behind Suspense boundaries.

```tsx
// next.config.ts
export default {
  cacheComponents: true
};

export default async function Page() {
  return <ProductPage />;
}
```

This replaces older “the whole route is static or dynamic” thinking with boundaries inside the component tree. Design those boundaries around freshness and personalization. A static shell should contain content safe to reuse, while request-specific data must stay outside shared caches.
