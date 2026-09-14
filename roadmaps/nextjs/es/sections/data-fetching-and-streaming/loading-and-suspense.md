# `loading.js` y Suspense Streaming

Un file `loading` crea una Suspense boundary en el route segment y loading UI inmediato durante navigation. Boundaries explícitas aíslan regiones lentas para que el resto streamee antes y siga interactivo.

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

Loading UI debe conservar structure y comunicar progreso sin grandes layout shifts. Coloca boundaries en secciones significativas, no en cada async function. Una dependency crítica puede necesitar bloquear si el contenido parcial sería engañoso.
