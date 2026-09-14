# Adapters and Platform Portability

Next.js 16.2 stabilized an Adapter API to improve collaboration across deployment providers. Adapters translate Next's output and server contracts to a host, but platform differences in caches, runtimes, image services, regional execution, and persistence still matter.

```tsx
// Platform adapters translate the Next.js build/runtime
// contract to a target host. Keep application code within
// APIs supported by every platform you promise to run on.
```

If portability is a requirement, test more than compilation. Exercise Server Actions, Route Handlers, streaming, cache invalidation, Proxy, images, and environment handling on each supported target. Isolate platform-specific integrations so switching a host does not require rewriting application domains.
