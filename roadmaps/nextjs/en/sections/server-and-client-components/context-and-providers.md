# Context and Providers

React context that depends on client state is provided by a Client Component. A Server Component layout can render that provider around server-rendered children, keeping the provider itself as narrow as possible while allowing interactive descendants to consume it.

```tsx
"use client";

export function ThemeProvider({ children }) {
  return <ThemeContext value="dark">{children}</ThemeContext>;
}

// Server layout can render the client provider around children.
```

Do not convert the root layout to a Client Component just to install one provider. Create a dedicated provider component and render it at the appropriate depth. Server Components cannot consume arbitrary client context during their server render, so shared server data should use server composition or data access instead.
