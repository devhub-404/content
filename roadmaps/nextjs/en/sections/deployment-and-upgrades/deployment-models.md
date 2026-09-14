# Deployment Models

Next.js can run on managed platforms, a Node.js server, containers, or platform adapters with varying support for server rendering, image optimization, caching, streaming, and Proxy. Static export is also possible for applications that do not require server features.

```tsx
# Standard production build
npm run build
npm run start

# Or use a supported platform adapter/deployment integration.
```

Deployment is part of the framework runtime. Verify persistent cache behavior, multi-instance coordination, file access, environment variables, streaming, and background work on the actual target. A build that starts locally does not prove a serverless or multi-region deployment preserves the same cache or filesystem assumptions.
