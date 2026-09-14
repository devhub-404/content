# Testando Tipos e Evitando Regressões

APIs de tipos podem regredir mesmo quando testes de runtime passam. Bibliotecas frequentemente adicionam fixtures de compile time ou type tests que verificam chamadas aceitas/rejeitadas, resultados inferidos e comportamento de declarations públicas. Pequeno projeto consumidor compilado em CI também encontra erros de packaging e resolução.

```ts
type Equal<A, B> =
  (<T>() => T extends A ? 1 : 2) extends
  (<T>() => T extends B ? 1 : 2)
    ? true
    : false;

type Expect<T extends true> = T;

type Test = Expect<Equal<ReturnType<typeof createUser>, User>>;
```

Não transforme toda implementação interna de tipos em teste frágil de igualdade exata; foque no comportamento público do qual consumidores dependem. Testes de runtime continuam necessários porque checker não valida dados reais de rede, efeitos colaterais, algoritmos ou integração emitida. Qualidade de produção precisa de evidência estática e de runtime.
