# Next.js 16.3 LTS, Upgrades e Security Releases

Em setembro de 2026, Next 16.3.3 é Active LTS e 15.5.24 Maintenance LTS. Next 16 trouxe mudanças como Cache Components e rename `middleware` para `proxy`, então major upgrade deve seguir migration guide, não só trocar package version.

```tsx
# Review the official upgrade guide, then use codemods where appropriate.
npx @next/codemod@latest upgrade latest

npm run build
npm test
```

Security releases podem exigir patch rápido mesmo sem feature changes. Acompanhe blog oficial, alinhe React, revise codemods e teste build, cache, server functions, routing e adapters após upgrade. Não permaneça em patch vulnerável por conveniência.
