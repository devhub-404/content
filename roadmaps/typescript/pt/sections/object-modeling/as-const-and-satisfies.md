# `as const` e `satisfies`

`as const` pede ao TypeScript para manter literals estreitos e tornar membros de objetos/arrays readonly no tipo inferido. É útil para lookup tables constantes, dados discriminantes e valores tuple-like onde widening para `string` ou arrays mutáveis perderia informação útil.

```ts
const routes = {
  home: "/",
  users: "/users",
} as const;

const palette = {
  primary: "#2457d6",
  danger: "#b42318",
} satisfies Record<string, `#${string}`>;
```

O operador `satisfies` verifica compatibilidade com tipo alvo preservando o tipo inferido mais específico da expressão. É excelente para objetos de configuração: você recebe validação da forma exigida sem forçar todas as propriedades a widened type da anotação. Nenhum recurso faz validação ou freeze em runtime.
