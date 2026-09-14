# Static Export

Static export produces HTML, CSS, JavaScript, and other assets that can be served without a Next.js server. It works for routes whose required data and behavior can be determined at build time and excludes server features that depend on request-time execution.

```tsx
// next.config.ts
export default {
  output: "export"
};
```

Choose static export for genuinely static deployment requirements, not as a performance trick for an application that needs sessions, dynamic Server Functions, or request-time personalization. Client-side APIs can still call external services, but credentials and authorization then belong to those external backends.
