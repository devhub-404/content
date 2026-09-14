# Dynamic Segments y Params

Las folders con brackets crean dynamic params. Catch-all/optional catch-all manejan paths profundos. En APIs actuales, route props como `params` son valores async en las conventions relevantes, así que haz await antes de usarlos.

```tsx
// app/products/[id]/page.tsx
export default async function Page({ params }) {
  const { id } = await params;
  const product = await getProduct(id);
  return <h1>{product.name}</h1>;
}
```

Valida params en la data boundary; una string de URL no prueba que la entity exista o que el user pueda acceder. Mantén canonical URLs y not-found explícitos, especialmente cuando slugs cambian o varios IDs apuntan al mismo record.
