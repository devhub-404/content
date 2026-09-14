# Parâmetros Optional, Rest e Destructured

Parâmetros opcionais usam `?`, parâmetros default podem tornar argumento efetivamente opcional para callers, e rest parameters modelam argumentos adicionais como array ou tuple. Parâmetros de objeto destructured são úteis para opções nomeadas, especialmente conforme API cresce.

```ts
type Options = {
  retries?: number;
  signal?: AbortSignal;
};

function request(
  url: string,
  { retries = 2, signal }: Options = {}
) {
  // ...
}

function sum(...values: number[]) {
  return values.reduce((a, b) => a + b, 0);
}
```

Mantenha optionality consistente com o comportamento de runtime. Um parâmetro `x?: T` pode receber `undefined`; default se aplica quando argumento está ausente ou explicitamente undefined. Prefira objeto de opções a muitos booleans posicionais ou parâmetros opcionais pouco relacionados porque nomes documentam call sites.
