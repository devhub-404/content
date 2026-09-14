# Server Components by Default

Pages and layouts in the App Router are Server Components by default. They can await databases or server APIs directly, use server-only dependencies, and render HTML/React payload without adding their component implementation to the client JavaScript bundle.

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

Fetch server data where the component needs it instead of creating an internal Route Handler and then calling your own server over HTTP. Keep server components focused on rendering and composition; move domain queries into reusable server modules when several routes use them.
