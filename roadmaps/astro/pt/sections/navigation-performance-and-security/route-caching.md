# Route Caching

Caching pode ocorrer no static build, route, CDN ou browser. Astro 7 amplia route caching em server apps, mas policy correta depende de response ser pública, personalizada, autenticada ou mutation-sensitive.

```astro
// Configure caching only for routes whose response semantics allow it.
export const prerender = false;

Astro.response.headers.set(
  "Cache-Control",
  "public, max-age=60, s-maxage=600"
);
```

Nunca cacheie output personalizado sob public key compartilhada. Defina cache identity/invalidation antes de perseguir hit rate. Static generation é cache mais simples quando data existe no build; runtime cache serve quando freshness e rendering request-time coexistem.
