# Type Predicates e Assertion Functions

User-defined type guard retorna type predicate como `value is User`, permitindo que teste de runtime reutilizável faça narrowing no caller. Assertion function com `asserts value is User` informa ao checker que retorno bem-sucedido garante o tipo afirmado.

```ts
function isUser(value: unknown): value is User {
  return (
    typeof value === "object" &&
    value !== null &&
    "id" in value &&
    "name" in value
  );
}

function assertUser(value: unknown): asserts value is User {
  if (!isUser(value)) throw new Error("Invalid user");
}
```

A anotação precisa descrever corretamente o teste de runtime. TypeScript confia no predicate mais do que consegue verificá-lo, então guard incorreto cria unsoundness. Para dados externos complexos, validators de schema que derivam ou integram tipos são mais seguros que checks manuais incompletos espalhados pelo código.
