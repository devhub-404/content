# Modelos de Deployment

Next puede ejecutarse en managed platforms, Node server, containers o adapters, con soporte variable para SSR, images, caching, streaming y Proxy. Static export sirve para apps sin server features.

```tsx
# Standard production build
npm run build
npm run start

# Or use a supported platform adapter/deployment integration.
```

Deployment forma parte del runtime. Verifica persistent cache, multi-instance coordination, filesystem, env vars, streaming y background work en el target real. Un build local no prueba las mismas assumptions en serverless/multi-region.
