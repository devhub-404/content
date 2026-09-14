# Adapters y Portabilidad de Plataforma

Next 16.2 estabilizó una Adapter API para deployment providers. Los adapters traducen output/server contracts al host, pero diferencias en cache, runtime, image services, regions y persistence siguen importando.

```tsx
// Platform adapters translate the Next.js build/runtime
// contract to a target host. Keep application code within
// APIs supported by every platform you promise to run on.
```

Si la portabilidad importa, prueba más allá de compilation. Ejercita Server Actions, Route Handlers, streaming, cache invalidation, Proxy, images y env en cada target. Aísla integrations específicas para no reescribir dominio al cambiar host.
