# Projetando uma API Pública de Tipos

Tipos públicos de biblioteca fazem parte do contrato de compatibilidade. Prefira nomes que expressem conceitos de domínio, mantenha generics ligados a relações reais e evite expor helper types internos apenas porque foram convenientes na implementação. Exporte a menor superfície realmente necessária aos consumidores.

```ts
export interface ClientOptions {
  baseUrl: string;
  signal?: AbortSignal;
}

export function createClient(
  options: ClientOptions
): Client;
```

Tipos estreitos demais tornam uso comum difícil; tipos amplos demais empurram erros para runtime. Modele variância de callbacks, nullabilidade, mutabilidade e resultados assíncronos deliberadamente. Depois de publicados, tipos podem causar breaking change mesmo sem mudança no JavaScript emitido, pois programas consumidores podem deixar de type-checkar.
