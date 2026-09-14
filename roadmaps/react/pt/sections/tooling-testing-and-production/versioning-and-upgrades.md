# React 19.3, Versionamento e Upgrades

React 19.3 é a release documentada atual em setembro de 2026. Minor releases podem adicionar features preservando major contract, mas frameworks que integram APIs low-level de RSC podem pin mais estritamente porque essas implementation APIs não seguem a mesma garantia semver.

```jsx
{
  "dependencies": {
    "react": "^19.3.0",
    "react-dom": "^19.3.0"
  }
}
```

Leia release notes oficiais, atualize `react` e `react-dom` juntos e teste hydration, forms, SSR e framework integrations. Prefira codemods/upgrade guidance do framework quando ele controla parte do build pipeline.
