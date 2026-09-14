# Static Export

Static export produz HTML/CSS/JS/assets servidos sem Next server. Funciona para routes cujos dados/comportamento podem ser determinados no build e exclui server features dependentes de request-time execution.

```tsx
// next.config.ts
export default {
  output: "export"
};
```

Escolha para deployment realmente static, não como performance trick para app com sessions, Server Functions ou personalization. Client ainda pode chamar external services, mas credentials/authorization pertencem ao backend externo.
