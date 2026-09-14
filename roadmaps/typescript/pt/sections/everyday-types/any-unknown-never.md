# `any`, `unknown` e `never`

`any` desativa grande parte da verificação do TypeScript e permite que operações inseguras se propaguem. Use em escape hatches deliberados, não como resposta padrão a um tipo difícil. `unknown` também pode conter qualquer valor, mas exige narrowing antes de operações que dependem de tipo mais específico.

```ts
function parse(value: string): unknown {
  return JSON.parse(value);
}

function fail(message: string): never {
  throw new Error(message);
}
```

`never` representa valores que não podem ocorrer, como função que sempre lança ou branch impossível após narrowing exaustivo. É especialmente útil para verificar tratamento completo de discriminated unions. Pense em `unknown` como “ainda não sei” e `never` como “não existe valor aqui”.
