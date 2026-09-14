# React 19.3, Versionado y Upgrades

React 19.3 es la release documentada actual en septiembre de 2026. Las minor releases pueden añadir features preservando el major contract, pero frameworks que integran APIs low-level de RSC pueden fijar versiones más estrictamente porque esas implementation APIs no siguen la misma garantía semver.

```jsx
{
  "dependencies": {
    "react": "^19.3.0",
    "react-dom": "^19.3.0"
  }
}
```

Lee release notes oficiales, actualiza `react` y `react-dom` juntos y prueba hydration, forms, SSR e integraciones. Prefiere codemods/upgrade guidance del framework cuando controle parte del build pipeline.
