# Constraints Genéricos

Generic constraint limita quais tipos podem substituir um type parameter preservando informação sobre o input específico. `T extends { length: number }` diz que callers podem passar qualquer tipo com length numérico, e dentro da função TypeScript sabe que a propriedade existe.

```ts
function getLength<T extends { length: number }>(value: T) {
  return value.length;
}

getLength("hello");
getLength([1, 2, 3]);
```

Constraints devem expressar a capacidade mínima exigida pela implementação. Restringir demais reduz reutilização e pode prejudicar inferência. Se a função só precisa de uma propriedade, restrinja essa propriedade em vez de exigir interface grande apenas porque callers atuais possuem uma.
