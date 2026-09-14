# Astro 7.3 y Upgrades

Astro 7.3 es la release actual en septiembre de 2026, después de que Astro 7 introdujera Rust compiler, Vite 8, advanced routing y route caching. Las minor releases añaden capabilities sin exigir adoptar todo.

```astro
# Recommended upgrade helper
npx @astrojs/upgrade

# Then verify
npm run build
npm run check
```

Usa upgrade tool/migration guide oficiales, luego ejecuta type checks, production build, route tests y adapter preview. Actualiza integrations compatibles en conjunto. Evita basar arquitectura central en experimental flags sin aceptar migration cost.
