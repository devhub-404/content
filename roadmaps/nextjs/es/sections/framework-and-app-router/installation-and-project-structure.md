# Instalación y Estructura de Proyecto

`create-next-app` crea un proyecto con TypeScript, linting, aliases y App Router según las options. El directory `app` contiene el route tree, mientras components, server modules, utilities y domain code pueden vivir fuera o junto a él.

```tsx
app/
  layout.tsx
  page.tsx
  globals.css
public/
next.config.ts
package.json
tsconfig.json
```

Mantén route files enfocados en routing/render/request boundaries en vez de poner toda implementación dentro de `app`. Colocation ayuda, pero route ownership y domain ownership no siempre son iguales. `public` mantiene paths estables; imported assets pasan por el build.
