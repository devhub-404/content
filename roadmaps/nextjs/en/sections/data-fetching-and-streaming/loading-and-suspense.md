# `loading.js` and Suspense Streaming

A `loading` file creates a route-segment Suspense boundary and immediate loading UI during navigation. Explicit Suspense boundaries inside a page can isolate slower regions so the rest of the route streams earlier and stays interactive.

```tsx
// app/dashboard/loading.tsx
export default function Loading() {
  return <DashboardSkeleton />;
}

// Fine-grained boundary inside a page
<Suspense fallback={<ChartSkeleton />}>
  <RevenueChart />
</Suspense>
```

Loading UI should preserve page structure and communicate progress without causing large layout shifts. Put boundaries around meaningful user-visible sections, not every async function. A slow critical dependency may still belong before the first render if showing incomplete content would be misleading.
