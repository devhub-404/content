# Adapters e Portabilidade de Plataforma

Next 16.2 estabilizou Adapter API para deployment providers. Adapters traduzem output/server contracts para host, mas diferenças em cache, runtime, image services, regions e persistence continuam importantes.

```tsx
// Platform adapters translate the Next.js build/runtime
// contract to a target host. Keep application code within
// APIs supported by every platform you promise to run on.
```

Se portabilidade importa, teste além de compilation. Exercite Server Actions, Route Handlers, streaming, cache invalidation, Proxy, images e env em cada target. Isole integrations específicas para não reescrever domínio ao trocar host.
