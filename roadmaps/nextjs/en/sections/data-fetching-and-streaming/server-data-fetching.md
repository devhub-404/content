# Fetching in Server Components

Server Components can use `fetch`, database clients, filesystems, or other server-side async APIs directly. In Next.js 16, data behavior depends on whether Cache Components is enabled and whether the operation is explicitly cached, so do not assume every fetch has the same caching semantics.

```tsx
export default async function Page() {
  const response = await fetch(process.env.PRODUCTS_API!);
  const products = await response.json();

  return <ProductList products={products} />;
}
```

Prefer direct database or service calls on the server when they are local to your backend instead of adding an HTTP hop through your own Route Handler. Validate errors and authorization close to the data source, and keep secrets out of values passed to Client Components.
