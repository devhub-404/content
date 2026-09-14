# Server Components por Default

Pages/layouts en App Router son Server Components por defecto. Pueden await databases/server APIs directamente, usar dependencies server-only y renderizar sin añadir su implementation al client bundle.

```tsx
export default async function Page() {
  const products = await db.product.findMany();

  return (
    <ul>
      {products.map(product => <li key={product.id}>{product.name}</li>)}
    </ul>
  );
}
```

Obtén server data donde el component la necesite en vez de crear un Route Handler interno y llamar tu propio server por HTTP. Mantén components enfocados en rendering/composition y extrae domain queries a server modules reutilizables.
