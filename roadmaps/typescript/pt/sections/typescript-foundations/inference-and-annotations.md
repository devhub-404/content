# Inferência e Anotações de Tipo

Inferência permite ao TypeScript derivar tipos de initializers, fluxo de controle, expressões de retorno, contexto esperado e relações genéricas. Você não precisa anotar toda variável. Anotações desnecessárias podem repetir informação e tornar refactoring mais ruidoso.

```ts
const count = 3;           // inferred as 3
let total = 0;             // inferred as number

function add(a: number, b: number) {
  return a + b;            // return type inferred as number
}
```

Anotações são mais úteis em fronteiras: parâmetros de funções públicas, APIs exportadas, variáveis intencionalmente amplas ou locais onde a inferência escolheria tipo diferente do design. Tipos de retorno frequentemente são inferíveis, mas anotações explícitas em funções exportadas documentam contrato estável e podem detectar mudanças acidentais de API.
