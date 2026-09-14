# O que TypeScript Adiciona ao JavaScript

TypeScript é JavaScript com sistema de tipos estático e camada de tooling. Ele verifica programas antes da execução, consegue inferir muitos tipos a partir de sintaxe JavaScript comum e remove sintaxe apenas de tipos ao emitir JavaScript. O runtime continua executando JavaScript, então TypeScript não altera o comportamento fundamental da linguagem.

```ts
function greet(name: string): string {
  return `Hello, ${name}`;
}

greet("Mina");
// greet(42); // type error
```

O typechecker encontra classes de erros como chamar valores incorretamente, acessar propriedades ausentes ou passar dados incompatíveis. Ele não prova todo fato de runtime, e dados externos continuam não confiáveis até serem validados. Aprenda a semântica de JavaScript primeiro; TypeScript descreve e verifica essa semântica em vez de substituí-la.
