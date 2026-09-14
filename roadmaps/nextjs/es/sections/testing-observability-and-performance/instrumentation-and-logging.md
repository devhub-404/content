# Instrumentation y Logging

La convention `instrumentation` ejecuta registration cuando inicia una server instance, útil para OpenTelemetry, error reporting, metrics y runtime monitoring. Los logs de producción deben incluir request/trace correlation en vez de console aislado.

```tsx
// instrumentation.ts
export async function register() {
  if (process.env.NEXT_RUNTIME === "nodejs") {
    await import("./instrumentation-node");
  }
}
```

La initialization debe ser segura en múltiples processes/serverless instances. Mantén secrets en server y evita startup blocking costoso. Observa route latency, external calls, cache behavior y errors para performance basada en evidencia.
