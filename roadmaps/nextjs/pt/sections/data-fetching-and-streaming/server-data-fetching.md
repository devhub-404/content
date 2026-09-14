# Fetch em Server Components

Server Components podem usar `fetch`, database clients, filesystem e outras async APIs diretamente. No Next 16, behavior depende de Cache Components e de caching explícito, então não presuma mesma semântica para todo fetch.

```tsx
export default async function Page() {
  const response = await fetch(process.env.PRODUCTS_API!);
  const products = await response.json();

  return <ProductList products={products} />;
}
```

Prefira DB/service call direta no server quando backend é local em vez de HTTP hop por Route Handler próprio. Valide errors/authorization perto da source e não passe secrets para Client Components.
