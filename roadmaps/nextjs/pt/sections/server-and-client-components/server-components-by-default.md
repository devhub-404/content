# Server Components por Default

Pages/layouts no App Router são Server Components por default. Podem await databases/server APIs diretamente, usar dependencies server-only e renderizar sem adicionar implementation ao client bundle.

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

Busque server data onde component precisa em vez de criar Route Handler interno e chamar seu próprio server por HTTP. Mantenha components focados em rendering/composition e extraia domain queries para server modules reutilizáveis.
