# Dynamic APIs e Dados Request-time

APIs como `cookies`, `headers` e search params leem values desconhecidos no build. Elas participam das decisões de dynamic rendering, especialmente com Cache Components onde request-time work precisa ficar isolado de conteúdo prerendered/cached.

```tsx
import { cookies } from "next/headers";

export default async function Page() {
  const cookieStore = await cookies();
  const theme = cookieStore.get("theme")?.value ?? "light";
  return <main data-theme={theme}>...</main>;
}
```

Leia request data apenas onde necessário. Dynamic access no root layout pode tornar grande parte do app request-dependent. Mantenha regiões personalizadas estreitas e use Suspense/cache boundaries conforme o modelo atual.
