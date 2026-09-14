# React 19.3, Versioning, and Upgrades

React 19.3 is the current documented React release as of September 2026. Minor releases can add features while preserving the major-version contract, but frameworks that integrate the lower-level Server Components bundler APIs may pin more strictly because those implementation APIs do not follow the same semver guarantee.

```jsx
{
  "dependencies": {
    "react": "^19.3.0",
    "react-dom": "^19.3.0"
  }
}
```

Read the official release notes before upgrades, update `react` and `react-dom` together, and test hydration, forms, server rendering, and framework integrations. Prefer codemods or framework upgrade guidance when an ecosystem tool owns part of the React build pipeline.
