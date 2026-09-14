# File-based Routing en SolidStart

SolidStart construye un framework full-stack sobre Solid/Solid Router. En v2, archivos bajo `src/routes` definen UI/API routes, con conventions para static, dynamic, optional y catch-all segments. Route nesting crea layouts y boundaries reutilizables.

```tsx
// src/routes/users/[id].tsx
export default function UserPage() {
  const params = useParams();
  return <h1>User {params.id}</h1>;
}
```

Usa file routing para expresar el URL tree, no la estructura interna de components. Mantén route-level data/server concerns cerca de la route cuando mejore ownership y extrae domain logic reutilizable. SolidStart v2 acompaña la migración mayor hacia Solid 2.
