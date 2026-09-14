# Static Export

Static export produce HTML/CSS/JS/assets servidos sin Next server. Funciona para routes cuyos datos/comportamiento pueden determinarse en build y excluye server features dependientes de request-time execution.

```tsx
// next.config.ts
export default {
  output: "export"
};
```

Elígelo para deployment realmente static, no como performance trick para una app con sessions, Server Functions o personalization. El client aún puede llamar external services, pero credentials/authorization pertenecen al backend externo.
