# `loading.js` e Suspense Streaming

File `loading` cria Suspense boundary no route segment e loading UI imediato em navigation. Boundaries explícitas isolam regiões lentas para o resto streamar antes e ficar interativo.

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

Loading UI deve preservar structure e comunicar progresso sem layout shifts grandes. Coloque boundaries em seções significativas, não em toda async function. Dependency crítica pode precisar bloquear quando conteúdo parcial seria enganoso.
