# File-based Routing no SolidStart

SolidStart constrói full-stack framework sobre Solid/Solid Router. No v2, arquivos em `src/routes` definem UI/API routes, com conventions para static, dynamic, optional e catch-all segments. Route nesting cria layouts e boundaries reutilizáveis.

```tsx
// src/routes/users/[id].tsx
export default function UserPage() {
  const params = useParams();
  return <h1>User {params.id}</h1>;
}
```

Use file routing para expressar URL tree, não estrutura interna de components. Mantenha route-level data/server concerns perto da route quando melhora ownership e extraia domain logic reutilizável. SolidStart v2 acompanha a migração maior para Solid 2.
