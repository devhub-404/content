# Lazy Components

`lazy` loads a component module only when it becomes necessary. The lazy component integrates with Suspense, letting a boundary show fallback UI while the code chunk is being fetched and initialized.

```tsx
const Settings = lazy(() => import("./Settings"));

<Suspense fallback={<p>Loading…</p>}>
  <Settings />
</Suspense>
```

Split code at meaningful feature or route boundaries rather than turning every small component into a separate request. Modern bundlers already perform tree shaking and route-level splitting in many setups. Measure the trade-off between initial bundle size, network request count, and navigation latency.
