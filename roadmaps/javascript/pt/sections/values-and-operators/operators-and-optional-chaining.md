# Operadores, Short-circuit e Optional Chaining

JavaScript possui operadores aritméticos, de assignment, comparação, lógicos, bitwise, condicionais, acesso a propriedade e outros com precedência e associatividade definidas. `&&` e `||` fazem short-circuit e retornam um dos operandos em vez de forçar boolean. O operador condicional é uma expressão para escolher entre dois valores.

```js
const canEdit = signedIn && permissions.includes("edit");
const label = compact ? "Save" : "Save changes";
const city = user.address?.city ?? "Unknown";

settings.theme ??= "system";
```

Optional chaining `?.` interrompe acesso ou chamada quando a base é nullish, e `??` fornece fallback apenas para valores nullish. Operadores de assignment lógico combinam short-circuit com atribuição. Parênteses são documentação barata sempre que várias famílias de operadores tornam o agrupamento difícil de lembrar.
