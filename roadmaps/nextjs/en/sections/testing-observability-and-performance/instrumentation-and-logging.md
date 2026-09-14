# Instrumentation and Logging

The `instrumentation` convention runs registration code when a Next.js server instance starts, which is useful for OpenTelemetry, error reporting, metrics, and runtime-specific monitoring setup. Production logs should include request and trace correlation rather than isolated console messages.

```tsx
// instrumentation.ts
export async function register() {
  if (process.env.NEXT_RUNTIME === "nodejs") {
    await import("./instrumentation-node");
  }
}
```

Instrumentation must be safe to initialize more than once across processes or serverless instances. Keep secrets in server configuration and avoid expensive blocking startup work unless necessary. Observe route latency, external calls, cache behavior, and errors so performance discussions are based on production evidence.
