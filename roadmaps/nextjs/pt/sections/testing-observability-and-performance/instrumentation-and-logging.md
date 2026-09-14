# Instrumentation e Logging

Convention `instrumentation` roda registration quando server instance inicia, útil para OpenTelemetry, error reporting, metrics e runtime monitoring. Logs de produção devem incluir request/trace correlation em vez de console isolado.

```tsx
// instrumentation.ts
export async function register() {
  if (process.env.NEXT_RUNTIME === "nodejs") {
    await import("./instrumentation-node");
  }
}
```

Initialization deve ser segura em múltiplos processes/serverless instances. Mantenha secrets no server e evite startup blocking caro. Observe route latency, external calls, cache behavior e errors para performance baseada em evidência.
