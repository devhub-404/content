# Context y Providers

React context dependiente de client state lo proporciona un Client Component. Un server layout puede renderizar el provider alrededor de children server-rendered, manteniendo la boundary estrecha y permitiendo a descendants interactivos consumir context.

```tsx
"use client";

export function ThemeProvider({ children }) {
  return <ThemeContext value="dark">{children}</ThemeContext>;
}

// Server layout can render the client provider around children.
```

No conviertas root layout en Client solo para instalar un provider. Crea un component dedicado a la profundidad adecuada. Los Server Components no consumen client context arbitrario durante server render; shared server data debe usar composition/data access server.
