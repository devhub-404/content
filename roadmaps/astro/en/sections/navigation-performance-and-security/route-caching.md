# Route Caching

Caching can happen at static-build level, application route level, CDN level, or browser level. Astro 7 expands route-caching capabilities for server-rendered applications, but the correct cache policy still depends on whether a response is public, personalized, authenticated, or mutation-sensitive.

```astro
// Configure caching only for routes whose response semantics allow it.
export const prerender = false;

Astro.response.headers.set(
  "Cache-Control",
  "public, max-age=60, s-maxage=600"
);
```

Never cache personalized output under a shared public key. Define cache identity and invalidation before chasing hit rates. Static generation remains the simplest cache when data can be known at build time; runtime caching is valuable when freshness and request-time rendering must coexist.
