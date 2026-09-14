# Dynamic Segments e Params

Folders com brackets criam dynamic params. Catch-all/optional catch-all tratam paths profundos. Nas APIs atuais, route props como `params` são valores async nas conventions relevantes, então faça await antes de usar.

```tsx
// app/products/[id]/page.tsx
export default async function Page({ params }) {
  const { id } = await params;
  const product = await getProduct(id);
  return <h1>{product.name}</h1>;
}
```

Valide params na data boundary; string da URL não prova que entity existe ou user pode acessá-la. Mantenha canonical URLs e not-found explícitos, especialmente quando slugs mudam ou vários IDs apontam ao mesmo record.
