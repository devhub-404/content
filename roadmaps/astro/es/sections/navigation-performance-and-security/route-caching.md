# Route Caching

Caching puede ocurrir en static build, route, CDN o browser. Astro 7 amplía route caching en server apps, pero la policy correcta depende de si la response es pública, personalizada, autenticada o mutation-sensitive.

```astro
// Configure caching only for routes whose response semantics allow it.
export const prerender = false;

Astro.response.headers.set(
  "Cache-Control",
  "public, max-age=60, s-maxage=600"
);
```

Nunca caches output personalizado bajo una public key compartida. Define cache identity/invalidation antes de perseguir hit rate. Static generation es la cache más simple cuando los datos existen en build; runtime cache sirve cuando freshness y rendering request-time deben coexistir.
