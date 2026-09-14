# Modelos de Deployment

Next pode rodar em managed platforms, Node server, containers ou adapters, com suporte variável a SSR, images, caching, streaming e Proxy. Static export serve a apps sem server features.

```tsx
# Standard production build
npm run build
npm run start

# Or use a supported platform adapter/deployment integration.
```

Deployment faz parte do runtime. Verifique persistent cache, multi-instance coordination, filesystem, env vars, streaming e background work no target real. Build local não prova mesmas assumptions em serverless/multi-region.
