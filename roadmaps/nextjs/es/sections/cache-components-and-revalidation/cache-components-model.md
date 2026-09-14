# Modelo de Cache Components

Con `cacheComponents`, Next mezcla static shell prerendered, trabajo explícitamente cached y request-time uncached en la misma route. Dynamic data no se bake automáticamente en el prerender; las regiones cached optan por el modelo y las regiones dinámicas streamean bajo Suspense.

```tsx
// next.config.ts
export default {
  cacheComponents: true
};

export default async function Page() {
  return <ProductPage />;
}
```

Esto sustituye el pensamiento “route entera static/dynamic” por boundaries en el component tree. Diseña según freshness/personalization. Static shell debe contener contenido seguro para reuse y request-specific data debe quedar fuera de shared caches.
