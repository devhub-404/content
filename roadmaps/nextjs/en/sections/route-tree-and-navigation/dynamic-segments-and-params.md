# Dynamic Segments and Params

Bracketed folders create dynamic route parameters. Catch-all and optional catch-all segments handle deeper path shapes. In current App Router APIs, route props such as `params` are async values in the relevant server component conventions, so await them before use.

```tsx
// app/products/[id]/page.tsx
export default async function Page({ params }) {
  const { id } = await params;
  const product = await getProduct(id);
  return <h1>{product.name}</h1>;
}
```

Validate route parameters at the data boundary; a string in the URL is not proof that the entity exists or that the user may access it. Keep canonical URLs and not-found behavior explicit, especially when slugs can change or several identifiers can map to one record.
