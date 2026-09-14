# Diseñar una API pública de tipos

Los tipos públicos de una biblioteca forman parte de su contrato de compatibilidad. Usa nombres de dominio claros, generics con relaciones reales y exporta solo la superficie que los consumidores necesitan. Los helper types internos no deberían filtrarse por accidente.

```ts
export interface ClientOptions {
  baseUrl: string;
  signal?: AbortSignal;
}

export function createClient(
  options: ClientOptions
): Client;
```

Tipos demasiado estrechos dificultan usos legítimos y tipos demasiado amplios desplazan errores a runtime. Cambiar una declaración pública puede ser breaking aunque el JavaScript emitido no cambie, porque programas consumidores pueden dejar de compilar.
