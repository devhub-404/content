# Next.js 16.3 LTS, Upgrades, and Security Releases

As of September 2026, Next.js 16.3.3 is the Active LTS security line and 15.5.24 is Maintenance LTS. Next 16 introduced important model changes including Cache Components and the `middleware` to `proxy` rename, so major upgrades should follow the official migration guide rather than only changing a package version.

```tsx
# Review the official upgrade guide, then use codemods where appropriate.
npx @next/codemod@latest upgrade latest

npm run build
npm test
```

Security releases can require prompt patch upgrades even when application features have not changed. Track the official blog, keep React compatibility aligned, run codemods carefully, and verify production builds, caching, server functions, routing, and deployment adapters after upgrades. Do not remain on a vulnerable patch for convenience.
