# Instalação e Estrutura de Projeto

`create-next-app` cria projeto com TypeScript, linting, aliases e App Router conforme options. Directory `app` contém route tree, enquanto components, server modules, utilities e domain code podem viver fora ou ao lado dela.

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

Mantenha route files focados em routing/render/request boundaries em vez de pôr toda implementação dentro de `app`. Colocation ajuda, mas route ownership e domain ownership nem sempre são iguais. `public` mantém paths estáveis; imported assets passam pelo build.
