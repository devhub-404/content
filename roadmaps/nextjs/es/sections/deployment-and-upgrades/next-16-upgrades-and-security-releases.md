# Next.js 16.3 LTS, Upgrades y Security Releases

En septiembre de 2026, Next 16.3.3 es Active LTS y 15.5.24 Maintenance LTS. Next 16 introdujo cambios como Cache Components y el rename `middleware` a `proxy`, así que un major upgrade debe seguir la migration guide, no solo cambiar package version.

```tsx
# Review the official upgrade guide, then use codemods where appropriate.
npx @next/codemod@latest upgrade latest

npm run build
npm test
```

Las security releases pueden exigir un patch rápido aunque no cambien features. Sigue el blog oficial, alinea React, revisa codemods y prueba build, cache, server functions, routing y adapters tras el upgrade. No permanezcas en un patch vulnerable por comodidad.
