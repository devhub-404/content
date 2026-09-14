# Modelo de Cache Components

Com `cacheComponents`, Next mistura static shell prerendered, trabalho explicitamente cached e request-time uncached na mesma route. Dynamic data não é automaticamente baked no prerender; regiões cached optam pelo modelo e regiões dinâmicas streamam sob Suspense.

```tsx
// next.config.ts
export default {
  cacheComponents: true
};

export default async function Page() {
  return <ProductPage />;
}
```

Isso substitui pensamento “route inteira static/dynamic” por boundaries na component tree. Projete por freshness/personalization. Static shell deve conter conteúdo seguro para reuse e request-specific data deve ficar fora de shared caches.
