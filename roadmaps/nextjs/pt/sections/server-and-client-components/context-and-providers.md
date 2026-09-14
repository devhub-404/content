# Context e Providers

React context dependente de client state é fornecido por Client Component. Server layout pode renderizar provider ao redor de children server-rendered, mantendo provider boundary estreita e permitindo descendants interativos consumirem context.

```tsx
"use client";

export function ThemeProvider({ children }) {
  return <ThemeContext value="dark">{children}</ThemeContext>;
}

// Server layout can render the client provider around children.
```

Não converta root layout em Client só para instalar provider. Crie component dedicado na profundidade adequada. Server Components não consomem client context arbitrário durante server render; shared server data deve usar composition/data access server.
