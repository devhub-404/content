# Dynamic APIs y Datos Request-time

APIs como `cookies`, `headers` y search params leen values desconocidos en build. Participan en decisiones de dynamic rendering, especialmente con Cache Components donde request-time work debe aislarse del contenido prerendered/cached.

```tsx
import { cookies } from "next/headers";

export default async function Page() {
  const cookieStore = await cookies();
  const theme = cookieStore.get("theme")?.value ?? "light";
  return <main data-theme={theme}>...</main>;
}
```

Lee request data solo donde sea necesaria. Dynamic access en root layout puede volver gran parte de la app request-dependent. Mantén regiones personalizadas estrechas y usa Suspense/cache boundaries según el modelo actual.
