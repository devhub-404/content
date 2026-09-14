# Type predicates y assertion functions

Un type guard propio devuelve un predicate como `value is User`, permitiendo reutilizar un check de runtime y estrechar el tipo del caller. Una assertion function con `asserts value is User` informa que, si retorna, la condición está garantizada.

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

TypeScript confía bastante en estas anotaciones y no puede demostrar que el cuerpo sea correcto. Un guard incorrecto introduce unsoundness. Para datos externos complejos, un schema validator integrado con tipos suele ser más seguro que muchos checks manuales incompletos.
