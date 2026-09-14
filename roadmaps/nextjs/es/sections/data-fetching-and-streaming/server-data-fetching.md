# Fetch en Server Components

Los Server Components pueden usar `fetch`, database clients, filesystem u otras async APIs directamente. En Next 16, el behavior depende de Cache Components y de caching explícito, así que no supongas la misma semántica para todo fetch.

```tsx
export default async function Page() {
  const response = await fetch(process.env.PRODUCTS_API!);
  const products = await response.json();

  return <ProductList products={products} />;
}
```

Prefiere DB/service calls directas en server cuando el backend sea local en vez de un HTTP hop por tu propio Route Handler. Valida errors/authorization cerca de la source y no pases secrets a Client Components.
